PORTNAME=	pystemmer
PORTVERSION=	2.0.1
PORTREVISION=	1
CATEGORIES=	textproc python
MASTER_SITES=	PYPI \
		http://snowball.tartarus.org/wrappers/
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}
DISTNAME=	PyStemmer-${PORTVERSION}

MAINTAINER=	dbaio@FreeBSD.org
COMMENT=	Snowball Stemming Algorithms for Information Retrieval
WWW=		https://pypi.org/project/PyStemmer/

LICENSE=	MIT BSD3CLAUSE
LICENSE_COMB=	dual

USES=		python
USE_PYTHON=	autoplist cython distutils

post-install:
	${STRIP_CMD} ${STAGEDIR}${PYTHONPREFIX_SITELIBDIR}/Stemmer*.so

.include <bsd.port.mk>
