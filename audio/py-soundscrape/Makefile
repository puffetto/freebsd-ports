PORTNAME=	soundscrape
DISTVERSION=	0.31.0
PORTREVISION=	1
CATEGORIES=	audio python
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	ports@FreeBSD.org
COMMENT=	SoundCloud downloader in python
WWW=		https://github.com/Miserlou/SoundScrape

LICENSE=	MIT
LICENSE_FILE=	${WRKSRC}/LICENSE

RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}mutagen>=1.31.0:audio/py-mutagen@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}soundcloud>=0.4.1:audio/py-soundcloud@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}args>=0.1.0:devel/py-args@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}clint>=0.3.2:devel/py-clint@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}demjson>=2.2.2:devel/py-demjson@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}fudge>=1.0.3:devel/py-fudge@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}simplejson>=3.3.1:devel/py-simplejson@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}wheel>=0.24.0:devel/py-wheel@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}requests>=2.9.0:www/py-requests@${PY_FLAVOR}

USES=		python
USE_PYTHON=	autoplist concurrent distutils

USE_GITHUB=	yes
GH_ACCOUNT=	Miserlou
GH_PROJECT=	SoundScrape
GH_TAGNAME=	800c1bfcad378d2de061e3b7964d59fe8b811862

NO_ARCH=	yes

.include <bsd.port.mk>
