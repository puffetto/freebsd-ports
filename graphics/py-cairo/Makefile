PORTNAME=	cairo
PORTVERSION=	1.28.0
PORTEPOCH=	1
CATEGORIES=	graphics python
MASTER_SITES=	https://github.com/pygobject/pycairo/releases/download/v${PORTVERSION}/
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}
DISTNAME=	py${PORTNAME}-${PORTVERSION}

MAINTAINER=	desktop@FreeBSD.org
COMMENT=	Python bindings for Cairo
WWW=		https://github.com/pygobject/pycairo

LICENSE=	LGPL21 MPL11
LICENSE_COMB=	multi
LICENSE_FILE_LGPL21=	${WRKSRC}/COPYING-LGPL-2.1
LICENSE_FILE_MPL11=	${WRKSRC}/COPYING-MPL-1.1

USES=		compiler:c11 gnome meson pkgconfig python
USE_PYTHON=	flavors py3kplist
USE_GNOME=	cairo
MESON_ARGS+=	-Dpython=${PYTHON_VERSION}

PORTSCOUT=	limitw:1,even

BINARY_ALIAS=	python3=${PYTHON_CMD}

PLIST_SUB=	PORTVER=${PORTVERSION}

post-install:
	${PYTHON_CMD} -m compileall -d ${PYTHON_SITELIBDIR} ${STAGEDIR}${PYTHON_SITELIBDIR}
	${PYTHON_CMD} -O -m compileall -d ${PYTHON_SITELIBDIR} ${STAGEDIR}${PYTHON_SITELIBDIR}
	@${STRIP_CMD} ${STAGEDIR}${PYTHON_SITELIBDIR}/cairo/_cairo*.so

.include <bsd.port.mk>
