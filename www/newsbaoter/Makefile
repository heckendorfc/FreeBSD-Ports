# $FreeBSD$

PORTNAME=	newsbaoter
PORTVERSION=	1.01
CATEGORIES=	www

MAINTAINER=	heckendorfc@gmail.com
COMMENT=	News feed reader

LICENSE=	BSD3CLAUSE

LIB_DEPENDS=	libcurl.so:${PORTSDIR}/ftp/curl

USE_GITHUB=	yes
GH_ACCOUNT=	heckendorfc

USES=		cmake ncurses
USE_GNOME=	libxml2 libxslt
USE_SQLITE=	yes

.include <bsd.port.mk>
