PORTNAME=	PGPLOT
PORTVERSION=	2.35
CATEGORIES=	graphics perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	perl@FreeBSD.org
COMMENT=	Perl5 extension which makes available the pgplot library
WWW=		https://metacpan.org/release/PGPLOT

LICENSE=	ART10 GPLv1+
LICENSE_COMB=	dual
LICENSE_FILE=	${WRKSRC}/LICENSE

BUILD_DEPENDS=	p5-Devel-CheckLib>0:devel/p5-Devel-CheckLib \
		p5-ExtUtils-F77>=1.13:lang/p5-ExtUtils-F77
LIB_DEPENDS=	libpgplot.so:graphics/pgplot \
		libpng.so:graphics/png

USES=		fortran perl5 xorg
USE_XORG=	x11

SCRIPTS_ENV=	PERL=${PERL}
INSTALL_TARGET=	pure_install
TEST_TARGET=	test

OPTIONS_DEFINE=	EXAMPLES

post-install:
	${STRIP_CMD} ${STAGEDIR}${PREFIX}/${SITE_ARCH_REL}/auto/PGPLOT/PGPLOT.so

post-install-EXAMPLES-on:
	@${MKDIR} ${STAGEDIR}${EXAMPLESDIR}
	(cd ${WRKSRC} && ${INSTALL_DATA} test* ${STAGEDIR}${EXAMPLESDIR})

.include <bsd.port.mk>
