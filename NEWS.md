* geepack v1.3.3 (2022-01-04) 

	* Minor documentation updates
	* Minor polishing of code


* geepack v1.3.2 (Release date: 2020-12-18)

	* NAMESPACE and all .Rd files are now auto generated.
	* PROTECT / UNPROTECT issue fixed (in file inter.cc)
	* Improved documentation of dietox.


* geepack v1.3.1 (Release date: 2019-12-13)

	* PROTECT / UNPROTECT imbalance fixed
	* Version 1.3-1 uploaded

* geepack v1.3.0 (Release date: 2019-12-10)

	* Migrated to use roxygen
   * Improved documentation of geeglm
   * Check for data being sorted by 'id' i geeglm; a warning is issued if not.
   * QIC added; thanks to Claus Ekstrøm who is now a contributor.
   * tidy function from broom package is imported.
   * muscatine data added
   * Version 1.3-0 uploaded

* geepack v1.2.1 (Release date: 2014-09-13)

	* geeglm objects now inherits from lm also (to prevent warning when
		calling predict).

* geepack v1.2.0 (Release date: 2014-09-13)

  * Maintainer of geepack is now Søren Højsgaard
  * Location of vignette fixed
  * Version 1.2-0 uploaded

* Legacy from when Jun Yan was maintainer:

2012-01-27  Jun Yan  <jun.yan@uconn.edu>

	* Commented out #undef NDEBUG in geesubs.cc.
	* Added a VecPrint function in utils.cc to print DVector;
	this replaces usage of cerr.

2012-01-09  Jun Yan  <jun.yan@uconn.edu>

	* Thank Jeffrey Horner <jeffrey.horner@vanderbilt.edu>
	and Cole Beck <cole.beck@vanderbilt.edu> for fixing the
	undefined symbol error (see 2011-11-14 entry:
	_Z5ValidIiEN3TNT6VectorIT_EERS3_RNS1_IiEE).
	The template function "Valid" (in original geesubs.cc)
	should actually be in the header file.
	This may fix the compilation error on ubuntu 11.10 too.

2011-11-21  Jun Yan  <jun.yan@uconn.edu>

	* Added an example to function relRisk.

2011-11-21  Jun Yan  <jun.yan@uconn.edu>

	* Added an example to function compCoef.

	* Changed the JSS paper year from 2005 to 2006 in CITATION.

2011-11-16  Jun Yan  <jun.yan@uconn.edu>

	* Added function relRisk for relative risk regression
	--- regression for binary response with log link.

	* Added function relRisk for relative risk regression
 	--- regression for binary response with log link.

	* Added function compCoef for comparing coefficients
	of the same sets of covariates between nested models.
	This implements the method of Yan, Aseltine, and Harel
	(2011, JEBS); for independent data, the method reduces
	to Allison (1995, American Journal of Sociology).

	* Fixed a bug in c++ code in constructing the working
	covariance structure using the regression model of scale.
	Simulation tests show improved efficiency in mean parameter
	estimation when scale regression is present.

2011-11-15 Soren Hojsgaard  <sorenh@mail.dk>

	* Dependence on the doBy package has been removed.

2011-11-14  Jun Yan  <jun.yan@uconn.edu>

        * Added NAMESPACE for to comply with the requirement of R-2.14.0.

	* Removed the "assert" lines in utils.cc in order not to crash R,
	which is quite rude practice. A "-DNDEBUG" has been added to the
	cppflags in Makevars for a better solution. Due to many asserts
	in tnt, we cannot get rid of the NOTE message completely:
	Found ‘_ZSt4cerr’, possibly from ‘std::cerr’ (C++)
	Found ‘__assert_fail’, possibly from ‘assert’ (C)

	* Added quote in statements like
	extract(m, "response") to get rid of NOTE:
	geese: no visible binding for global variable ‘response’

	* Added a line of
	#undef NDEBUG
	to the beginning of geesubs.cc; thank Brian Ripley for the NMU.
	Still unclear why the error without this line:
	undefined symbol: _Z5ValidIiEN3TNT6VectorIT_EERS3_RNS1_IiEE


2011-02-23  Søren Højsgaard <sorenh@agrsci.dk>

	* In geeglm is checked if the model matrix is rank deficient; if
	so then geeglm exits. Thanks to Jason D Thorpe for pointing this out.

	* Bug in anova fixed. Thanks to Stefan Boehringer for pointing
	this out.

	* Version 1.0-18 uploaded.


2010-01-26  Søren Højsgaard <sorenh@agrsci.dk>

	* fixed2Zcor function has been added. This function makes it
	easier to work with a fixed correlation matrix (in particular when
	cluster sizes are not equal).

	* A vignette on models with unequal cluster size, fixed
	correlation matrices etc. has been added.

	* Version 1.0-17 uploaded

2008-12-08  Søren Højsgaard <sorenh@agrsci.dk>

	* Bugfix in 1.0.15 caused problem in binomial case using
	cbind(pos,neg). Thanks to Tobias Verbeke. Fixed now.

	* Bugfix in 1.0.15 caused problem when using variables derived
	from gam package call to geeglm. Thanks to Eric Rexstad. Fixed now.

	* Using scale.fix argument gave problem in geeglm. Thanks to
	Tobias Verbeke. Fixed now.

	* Fitting large data set with binomial model and 3 measurements
	per unit using unstructured correlation crashes R. Thanks to
	Tobias Verbeke. Problem has *NOT* been solved but a remark has
	been added to doc file.

	* Version 1.0-16 uploaded

2008-12-01  Søren Højsgaard <sorenh@agrsci.dk>

	* When a factor has unused levels, the underlying C code
	fails. This is now catured in geeglm. Thanks to Janet Young

	* tests directory added to package

	* Version 1.0-15 uploaded

2007-07-13  Søren Højsgaard <sorenh@agrsci.dk>

	* Smaller 'standardization' changes implemented. Thanks to Achim

	* Version 1.0-14 uploaded

2007-03-21  Søren Højsgaard <sorenh@agrsci.dk>

	* A remark on fixed correlation structures has been added to the
	geeglm.Rd doc file.

	* A Wishlist file has been added

	* Version 1.0-13 uploaded

2007-03-21  Søren Højsgaard <sorenh@agrsci.dk>

	* Bug in geeglm fixed so that it now works with a fixed
	correlation structure. Thanks to Ulrich Halekoh for the fix.


2006-02-13  Jun Yan  <jyan@stat.uiowa.edu>

	* Bug in genZcor and genZodds fixed. 
	Thanks to Chongzhi Di <cdi@jhsph.edu>. 
	Previously, the matrice generated by genZcor/genZodds are 
	wrong when the number of unique waves is greater than or
	equal to 10.

2006-01-24 Søren Højsgaard <sorenh@agrsci.dk>

	* Bug in anova.geeglm fixed (showed up when there was only one
	term on the right hand side of ~). 

	* geeglm only works on complete data. This has been pointed out in
	the man pages. (At some point of time, a proper na.action should be
	taken). 

	* All datasets are saved as .txt files (previously some were saved
	as .rda files but that caused problems in building the package on
	windows xp).

2005-08-13  Jun Yan  <jyan@stat.uiowa.edu>

	* The working correlation structure can now be "fixed".


2005-06-13 Søren Højsgaard <sorenh@agrsci.dk>

	* Søren Højsgaard has modified the geeglm function so that it can
	take the 'waves' argument which is used for explicitely specifying
	the ordering of repeated measurements on the same unit. geeglm can
	also take the 'zcor' argument for a user defined working
	correlation structure. 

	* A documentation file for the genZcor
	function has been added. 

	* All data sets provided are now saved as
	text files.

	* ordgee has been modified to check if the response variable is an
	ordered factor.

	* geeglm can now take the argument std.err which specifies the
	type of variance estimate to be calculated.

2005-05-11 Søren Højsgaard <sorenh@agrsci.dk>

	* Søren Højsgaard has modified the anova function to make it
	calculate the correct degrees of freedom.


2005-04-11  Jun Yan  <jyan@stat.uiowa.edu>

	* Søren Højsgaard made some minor changes to geeglm - 
	basically, that geese.control did not work. Now it does.


2005-02-09  Jun Yan  <jyan@stat.uiowa.edu>

	* Søren Højsgaard joined the development with geeglm, which 
	"works like" glm and returns an object which is similar to 
	a glm object. Residuals and predicted values can be extracted
	using the generic functions as with a glm object. 

	* An important feature of geeglm, is that an anova method 
	exists for these models.

