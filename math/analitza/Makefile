# $NetBSD: Makefile,v 1.38 2018/01/01 21:18:09 adam Exp $

DISTNAME=	analitza-${_KDE_VERSION}
PKGREVISION=	11
CATEGORIES=	math
COMMENT=	KDE library for mathematical features

.include "../../meta-pkgs/kde4/Makefile.kde4"

BROKEN_READLINE_DETECTION=	yes

.include "../../meta-pkgs/kde4/kde4.mk"

.include "../../devel/readline/buildlink3.mk"
.include "../../devel/ncurses/buildlink3.mk"
.include "../../x11/kdelibs4/buildlink3.mk"

.include "../../mk/bsd.pkg.mk"
