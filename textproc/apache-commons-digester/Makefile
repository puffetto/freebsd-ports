PORTNAME=	commons-digester
PORTVERSION=	2.1
PORTREVISION=	2
CATEGORIES=	textproc java devel
MASTER_SITES=	APACHE_COMMONS_BINARIES
PKGNAMEPREFIX=	apache-
DISTNAME=	${PORTNAME}-${PORTVERSION}-bin

MAINTAINER=	ports@FreeBSD.org
COMMENT=	XML-to-Java-object mapping utility package
WWW=		https://commons.apache.org/proper/commons-digester/

LICENSE=	APACHE20
LICENSE_FILE=	${WRKSRC}/LICENSE.txt

BUILD_DEPENDS=	${JAR_DEPENDS}
RUN_DEPENDS=	${JAR_DEPENDS}

USES=		java

WRKSRC=		${WRKDIR}/${PORTNAME}-${PORTVERSION}
NO_BUILD=	yes
NO_ARCH=	yes

JARFILE=	${PORTNAME}.jar
PLIST_FILES=	${JAVAJARDIR}/${JARFILE}

OPTIONS_DEFINE=	DOCS

OTHERDOCS=	LICENSE.txt NOTICE.txt RELEASE-NOTES.txt
PORTDOCS=	*

.include <bsd.port.pre.mk>

JAR_DEPENDS=	${JAVALIBDIR}/commons-beanutils.jar:java/apache-commons-beanutils \
		${JAVALIBDIR}/commons-logging.jar:java/apache-commons-logging \
		${JAVALIBDIR}/commons-collections.jar:java/apache-commons-collections \
		${JAVALIBDIR}/xercesImpl.jar:textproc/xerces-j

do-install:
	@${ECHO_MSG} -n ">> Installing JAR as ${JAVAJARDIR}/${JARFILE}..."
	${INSTALL_DATA} ${WRKSRC}/${PORTNAME}-${PORTVERSION}.jar ${STAGEDIR}${JAVAJARDIR}/${JARFILE}
	@${ECHO_MSG} " [ DONE ]"

do-install-DOCS-on:
	@${ECHO_MSG} -n ">> Installing documentation in ${DOCSDIR}..."
	@cd ${WRKSRC}/apidocs \
	  && ${FIND} . -type d -exec ${MKDIR} ${STAGEDIR}${DOCSDIR}/{} \; \
	  && ${FIND} . -type f -exec ${INSTALL_DATA} {} ${STAGEDIR}${DOCSDIR}/{} \;
	${INSTALL_DATA} ${OTHERDOCS:S,^,${WRKSRC}/,} ${STAGEDIR}${DOCSDIR}/
	@${ECHO_MSG} " [ DONE ]"

.include <bsd.port.post.mk>
