# $FreeBSD$

PORTNAME=	newsbaoter
PORTVERSION=	0.1
CATEGORIES=	www

MAINTAINER=	heckendorfc@gmail.com
COMMENT=	News feed reader

LICENSE=	BSD3CLAUSE

LIB_DEPENDS=	libcurl.so:${PORTSDIR}/ftp/curl

USE_GITHUB=	yes
GH_ACCOUNT=	heckendorfc
GH_COMMIT=	5459e7f
GH_TAGNAME=	${GH_COMMIT}

USES=		cmake ncurses
USE_GNOME=	libxml2 libxslt
USE_SQLITE=	yes

.include <bsd.port.mk>
