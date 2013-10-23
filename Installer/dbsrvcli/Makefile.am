#### Makefile.am
#### Top-level Makefile.am

#### Created by Laurence D. Finston (LDF) 2008.06.19.

#### Copyright (C) 2009, 2010, 2011 Gesellschaft fuer wissenschaftliche Datenverarbeitung mbH

#### Copied from `quali' and adapted for use for `optdbsrv' and `optdbcli'.
#### LDF 2009.09.23.
   
#### $Id: Makefile.am 7466 2012-03-16 11:30:42Z finston $

#### * (1) Top

ACLOCAL_AMFLAGS = "-I m4"

#### ** (2) bin_PROGRAMS 

bin_PROGRAMS = dbsrvcli$(EXEEXT) 

#### optdbcli$(EXEEXT) 

dbsrvcli_SOURCES = dbsrvcli.c


#### ** (2) Variables for subdirectories.
#### 
#### LDF 2008.06.23.

SOURCEDIR = src
CWEBDIR   = CWEB

export SOURCEDIR
export CWEBDIR   

SUBDIRS = $(CWEBDIR) $(SOURCEDIR)

export abs_top_builddir

#### ** (2)


#### *** (3) EXTRA_DIST 
####        (additional files to be included in the distribution)

EXTRA_DIST = flwchrt.mp flwchrt.tex optcnfg.h opt_delete_logs.sh

#### Generating these files requires MetaPost, which may not be installed.
#### However, these files aren't very important, so I'm removing them
#### from `EXTRA_DIST'.  Anyone who wants to look at the flowchart
#### can generate them provided MetaPost is installed.  TeX must be
#### installed because of the CWEB and Texinfo files.
#### LDF 2009.12.16.
#### flwchrt.dvi flwchrt.pdf flwchrt.ps

#### ** (2) Rules

#### *** (3) clean-local

# clean-local:
# 	@rm -f rplcvars.c++ rplcvars.l++ rplcvars.tex rplcvars.dvi \
#                rplcvars.ps rplcvars.pdf \
#                rplcvars.idx rplcvars.log rplcvars.scn rplcvars.toc

# all-local: rplcvars.tex rplcvars.dvi rplcvars.ps rplcvars.pdf 

# mostlyclean-local: 
# 	@rm -f rplcvars.c++ rplcvars.l++ \
#                rplcvars.idx rplcvars.log rplcvars.scn rplcvars.toc

#### *** (3) Rules 

flwchrt.1: flwchrt.mp
	mpost flwchrt.mp

flwchrt.dvi: flwchrt.tex flwchrt.1
	tex flwchrt.tex

flwchrt.ps: flwchrt.dvi 
	dvips -o flwchrt.ps flwchrt.dvi

flwchrt.pdf: flwchrt.ps
	ps2pdf flwchrt.ps


#### **** (4)

#### *** (3)

#### *** (3) query

.PHONY: query

query: 
	echo "HAVE_TEX == $(HAVE_TEX)"
	$(MAKE) query -C $(SOURCEDIR)
	@echo "abs_top_builddir == $(abs_top_builddir)"
	@echo "abs_builddir == $(abs_builddir)"
# 	@echo "FC == $(FC)"
# 	@echo "F77 == $(F77)"
# 	@echo "CC == $(CC)"
# 	@echo "QUALI_SEND_TO_ADDRESS == $(QUALI_SEND_TO_ADDRESS)"
# 	@echo "QUALI_SEND_TO_ADDRESS == @QUALI_SEND_TO_ADDRESS@"
# 	@echo "POSTGRESQL_FLAGS == $(POSTGRESQL_FLAGS)"
# 	@echo "POSTGRESQL_FLAGS == @POSTGRESQL_FLAGS@"
# 	@echo "CTANGLE == $(CTANGLE)"
# 	@echo "CWEAVE == $(CWEAVE)"
# 	@echo "cweave == "`type cweave`
# 	$(MAKE) query -C $(WEBSERVERDIR)
#	$(MAKE) query -C $(USERADMINDIR)


#### *** (3)

#### ** (2) End of top-level `Makefile.am'

#### * (1) Local variables for Emacs

#### Local Variables:
#### mode:Makefile
#### abbrev-mode:t
#### eval:(read-abbrev-file)
#### eval:(outline-minor-mode t)
#### outline-regexp:"#### [*\\f]+[ \\t]+([0-9]+)"
#### End:
