# $NetBSD: Makefile,v 1.36 2016/05/04 10:29:17 ryoon Exp $
#

DISTNAME=	djview-4.10.6
PKGNAME=	${DISTNAME:S/djview/djview4/}
CATEGORIES=	graphics
MASTER_SITES=	${MASTER_SITE_SOURCEFORGE:=djvu/}

MAINTAINER=	pkgsrc-users@NetBSD.org
HOMEPAGE=	http://djvu.sourceforge.net/
COMMENT=	Portable DjVu viewer and browser plugin
LICENSE=	gnu-gpl-v2

GNU_CONFIGURE=	yes
USE_LANGUAGES=	c c++
USE_LIBTOOL=	yes
USE_TOOLS+=	gmake pkg-config

SUBST_CLASSES+=		nsdejavu
SUBST_STAGE.nsdejavu=	post-patch
SUBST_MESSAGE.nsdejavu=	Fixing hardcoded paths.
SUBST_FILES.nsdejavu=	nsdejavu/nsdejavu.c
SUBST_SED.nsdejavu=	-e 's:/usr/local/lib:${LOCALBASE}/lib:'

.include "../../graphics/djvulibre-lib/buildlink3.mk"
.include "../../x11/qt4-libs/buildlink3.mk"
.include "../../x11/qt4-tools/buildlink3.mk"
.include "../../graphics/tiff/buildlink3.mk"
.include "../../mk/jpeg.buildlink3.mk"
.include "../../mk/bsd.pkg.mk"
