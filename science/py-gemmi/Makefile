PORTNAME=	gemmi
DISTVERSIONPREFIX=	v
DISTVERSION=	0.7.1
CATEGORIES=	science python
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	yuri@FreeBSD.org
COMMENT=	Macromolecular crystallography library and utilities
WWW=		https://gemmi.readthedocs.io/en/latest/

LICENSE=	MPL20
LICENSE_FILE=	${WRKSRC}/LICENSE.txt

BUILD_DEPENDS=	${PYTHON_PKGNAMEPREFIX}pip>0:devel/py-pip@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}nanobind>0:devel/py-nanobind@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}wheel>0:devel/py-wheel@${PY_FLAVOR} \
		pybind11>=2.6:devel/pybind11
LIB_DEPENDS=	libgemmi_cpp.so:science/gemmi
TEST_DEPENDS=	${PYTHON_PKGNAMEPREFIX}biopython>0:biology/py-biopython@${PY_FLAVOR}

USES=		cmake compiler:c++17-lang localbase:ldflags python
USE_PYTHON=	flavors

USE_GITHUB=	yes
GH_ACCOUNT=	project-gemmi

CMAKE_ON=	USE_PYTHON
CMAKE_OFF=	BUILD_GEMMI_PROGRAM STANDALONE_PYTHON_MODULE
CMAKE_ARGS=	-DPython_EXECUTABLE=${PYTHON_CMD}

TEST_ENV=	${MAKE_ENV} PYTHONPATH=${STAGEDIR}${PYTHONPREFIX_SITELIBDIR}
TEST_WRKSRC=	${BUILD_WRKSRC}/tests

PLIST_SUB=	VER=${PORTVERSION}

do-test:
	@cd ${WRKSRC} && ${SETENV} ${TEST_ENV} ${PYTHON_CMD} -m unittest discover -v tests/

.include <bsd.port.mk>
