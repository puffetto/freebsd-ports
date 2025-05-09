PORTNAME=	facter
PORTVERSION=	3.14.24
PORTREVISION=	9
CATEGORIES?=	sysutils
MASTER_SITES=	https://downloads.puppetlabs.com/facter/

MAINTAINER=	puppet@FreeBSD.org
COMMENT=	Cross-platform library for retrieving facts from OS
WWW=		https://puppetlabs.com/facter

LICENSE=	APACHE20
LICENSE_FILE=	${WRKSRC}/LICENSE

BROKEN=		fails to build with Boost>=1.87
BROKEN_DragonFly=	DragonFly is not supported upstream
DEPRECATED=	Reached EOL
EXPIRATION_DATE=2025-05-09

LIB_DEPENDS=	libboost_system.so:devel/boost-libs \
		libcurl.so:ftp/curl \
		libleatherman_locale.so:devel/leatherman \
		liblibcpp-hocon.so:devel/cpp-hocon \
		libyaml-cpp.so:devel/yaml-cpp

CONFLICTS_INSTALL=	rubygem-facter

PLIST_SUB=	PORTVERSION="${PORTVERSION}"

USES=		cmake:noninja compiler:c++11-lib cpe ruby ssl
CPE_VENDOR=	puppet
USE_LDCONFIG=	yes
CMAKE_OFF=	ENABLE_CXX_WERROR

OPTIONS_DEFINE=	FACTER_JAVA
FACTER_JAVA_DESC=	Build with Java bindings for puppetserver
FACTER_JAVA_USES=	java:build
FACTER_JAVA_CMAKE_ON=	-DJAVA_HOME=${JAVA_HOME}

OPTIONS_DEFAULT=	FACTER_JAVA

OPTIONS_SUB=	yes

.include <bsd.port.options.mk>

post-patch:
	@${REINPLACE_CMD} -e 's|%%PREFIX%%|${PREFIX}|g' \
		${WRKSRC}/lib/src/facts/posix/collection.cc \
		${WRKSRC}/lib/src/util/config/posix/config.cc

post-install:
	${MKDIR} ${STAGEDIR}${PREFIX}/lib/ruby/gems/${RUBY_VER}/specifications
	${INSTALL_DATA} ${WRKSRC}/.gemspec ${STAGEDIR}${PREFIX}/lib/ruby/gems/${RUBY_VER}/specifications/${DISTNAME}.gemspec

test: build
	cd ${WRKSRC}/lib && bundle install --path vendor
	cd ${CONFIGURE_WRKSRC} && ${MAKE_CMD} test

.include <bsd.port.mk>
