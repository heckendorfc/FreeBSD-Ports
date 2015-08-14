# $FreeBSD$

PORTNAME=	angband
PORTVERSION=	4.0.1
CATEGORIES=	games
PKGNAMESUFFIX=	4

MAINTAINER=	heckendorfc@gmail.com
COMMENT=	Rogue-like game with color, X11 support

LICENSE=	GPLv2

USE_GITHUB=	yes
GH_ACCOUNT=	angband
GH_PROJECT=	angband
GH_TAGNAME=	${PORTVERSION}

OPTIONS_DEFINE=	SDL X11 DOCS
OPTIONS_DEFAULT=X11

USES=		autoreconf gmake ncurses
GNU_CONFIGURE=	yes
CONFIGURE_ENV=	ac_cv_path_NCURSES_CONFIG=${TRUE}
CONFIGURE_ARGS=	--localstatedir=/var

CPPFLAGS+=	-I${NCURSESINC}
LDFLAGS+=	-L${NCURSESLIB} -lncursesw

DOCS_BUILD_DEPENDS=	rst2html:${PORTSDIR}/textproc/py-docutils

SDL_USE=		SDL=image,mixer,ttf,sdl
SDL_CONFIGURE_ENABLE=	sdl

X11_USE=		XORG=sm,x11
X11_RUN_DEPENDS=	xorg-fonts-miscbitmaps>=0:${PORTSDIR}/x11-fonts/xorg-fonts-miscbitmaps
X11_CONFIGURE_ENABLE=	x11

WRKSRC=		${WRKDIR}/angband-${PORTVERSION}

post-patch:
	@${REINPLACE_CMD} -e \
		's|-Wno-missing-field-initializers || ; \
		 s|/games$$|/bin|' ${WRKSRC}/configure.ac
	@${REINPLACE_CMD} -e \
		's|.SILENT:||' ${WRKSRC}/mk/buildsys.mk.in
	@${REINPLACE_CMD} -e \
		's|-O0||' ${WRKSRC}/src/Makefile

post-install:
	@${STRIP_CMD} ${STAGEDIR}${PREFIX}/bin/angband
.for i in apex save user
	@${MKDIR} ${STAGEDIR}${DATADIR}/${i}
.endfor

.include <bsd.port.mk>
