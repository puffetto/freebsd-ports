PORTNAME=	actionview
PORTVERSION=	7.0.8.7
CATEGORIES=	devel rubygems
MASTER_SITES=	RG
PKGNAMESUFFIX=	70

MAINTAINER=	sunpoet@FreeBSD.org
COMMENT=	Simple, battle-tested conventions and helpers for building web pages
WWW=		https://github.com/rails/rails/tree/main/actionview \
		https://rubyonrails.org/

LICENSE=	MIT
LICENSE_FILE=	${WRKSRC}/MIT-LICENSE

RUN_DEPENDS=	rubygem-activesupport70>=${PORTVERSION}<${PORTVERSION}_99:devel/rubygem-activesupport70 \
		rubygem-builder>=3.1<4:devel/rubygem-builder \
		rubygem-erubi>=1.4<2:www/rubygem-erubi \
		rubygem-rails-dom-testing-rails70>=2.0<3:textproc/rubygem-rails-dom-testing-rails70 \
		rubygem-rails-html-sanitizer>=1.2.0<2:textproc/rubygem-rails-html-sanitizer

USES=		cpe gem

NO_ARCH=	yes

CPE_VENDOR=	rubyonrails

PORTSCOUT=	limit:^7\.0\.

.include <bsd.port.mk>
