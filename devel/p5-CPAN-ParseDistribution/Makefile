# $NetBSD: Makefile,v 1.6 2017/06/05 14:22:38 ryoon Exp $
#

DISTNAME=	CPAN-ParseDistribution-1.54
PKGNAME=	p5-${DISTNAME}
PKGREVISION=	1
CATEGORIES=	devel
MASTER_SITES=	${MASTER_SITE_PERL_CPAN:=CPAN/}

MAINTAINER=	pkgsrc-users@NetBSD.org
HOMEPAGE=	http://search.cpan.org/dist/CPAN-ParseDistribution/
COMMENT=	Index a file from the BackPAN to give name and version of the distr'n
LICENSE=	${PERL5_LICENSE}

# for make test
BUILD_DEPENDS+=	p5-Devel-CheckOS-[0-9]*:../../devel/p5-Devel-CheckOS
BUILD_DEPENDS+=	p5-Parallel-ForkManager-[0-9]*:../../devel/p5-Parallel-ForkManager
BUILD_DEPENDS+=	p5-Test-Requires-[0-9]*:../../devel/p5-Test-Requires
BUILD_DEPENDS+=	p5-YAML-[0-9]*:../../textproc/p5-YAML
BUILD_DEPENDS+= p5-Archive-Zip-[0-9]*:../../archivers/p5-Archive-Zip

PERL5_PACKLIST=	auto/CPAN/ParseDistribution/.packlist
USE_LANGUAGES=	# none

.include "../../lang/perl5/module.mk"
.include "../../mk/bsd.pkg.mk"
