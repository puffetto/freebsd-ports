PORTNAME=	papirus-icon-theme
PORTVERSION=	20250501
CATEGORIES=	x11-themes

MAINTAINER=	tagattie@FreeBSD.org
COMMENT=	Papirus icon theme
WWW=		https://git.io/papirus-icon-theme

LICENSE=	GPLv3
LICENSE_FILE=	${WRKSRC}/LICENSE

USES=		gmake

USE_GITHUB=	yes
GH_ACCOUNT=	PapirusDevelopmentTeam

NO_ARCH=	yes
NO_BUILD=	yes

PORTDOCS=	AUTHORS CHANGELOG.md README.md

OPTIONS_DEFINE=	DOCS

post-install:
	@cd ${STAGEDIR}${PREFIX} && \
		${FIND} share/icons -type f -o -type l >> ${TMPPLIST}

post-install-DOCS-on:
	@${MKDIR} ${STAGEDIR}${DOCSDIR}
	${INSTALL_MAN} ${PORTDOCS:S|^|${WRKSRC}/|} ${STAGEDIR}${DOCSDIR}

.include <bsd.port.mk>
