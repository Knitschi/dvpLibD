
include(cpfInitPackageProject)
include(cpfAddCppPackage)

cpfInitPackageProject()

set( briefDescription "A helper package that I use for experiments related to the dependency versioning problem." )
set( longDescription "" )


set( PACKAGE_PUBLIC_HEADER
	MyFunction.h
)

set( PACKAGE_PRODUCTION_FILES
	MyFunction.cpp
) 

cpfGetUnversionedPackageName(isVersionedName unversionedName versionPostfix ${PROJECT_NAME})

############################################## Add Package #################################
cpfAddCppPackage( 
	TYPE					LIB
	OWNER 					Knitschi
	BRIEF_DESCRIPTION		${briefDescription}
	LONG_DESCRIPTION		${longDescription}
	PACKAGE_NAMESPACE		${unversionedName}
	PUBLIC_HEADER			${PACKAGE_PUBLIC_HEADER}
	PRODUCTION_FILES		${PACKAGE_PRODUCTION_FILES}
)

cpfSetupInCodeVersionMechanism()

