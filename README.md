# com.epistimis.uddl.query.parent
UDDL Query Language

UDDL was developed as part of the Future Airborne Capability Environment (FACE) work originally commissioned by the US Navy and eventually supported by the USAF and USArmy.  Interest in UDDL generally resulted in a decision to split it out of FACE for general use.

The [current specification is available](https://publications.opengroup.org/standards/face/c198) for free after to you create an [OpenGroup](https://www.opengroup.org) account.  This repo implements the UDDL Query Language (chapter 6). 
It currently does not support all the constraints described in chapter 6.2. (Want to tackle that?)

This code is based on that spec but is 'unofficial'. It does not use the namespace/packaging from the original spec which results in some minor modifications to OCL. It does not use the official .ecore model though the generated model should be compatible with it. Other than that, it should be functionally equivalent.

Note that, except for package naming, the UDDL Query grammar is the same as the spec. 

# Getting started

See the [UDDL Getting Started Guide]([GETTING_STARTED.md](https://github.com/Epistimis/com.epistimis.uddl.parent/blob/0478f25fcb65772d6c26a104481c982113e73c20/GETTING_STARTED.md)) for info on setting up an Eclipse development environment. It will take you all the way to a working demo.

# Security and Bug Reports
For most bugs, create a GitHub issue. If you believe you have found a security issue, see [Security[(SECURITY.md) for reporting instructions.

# User Doc
While this implements the UDDL Query language (chapter 6.1) exactly, the UDDL spec contains only the grammar. It does not explain anything. There is some
explanation in the FACE Reference Implementation Guide, Vol 3. This document, however, is not yet generally available. You must be a FACE Consortium member
to get a copy.  Doc will be added soon.

In the meantime, you can get a basic understanding by thinking about it this way: The UDDL Query Language is an SQL dialect with one big difference: SQL
as used with an RDBMS (Oracle, MySQL, etc.) is a dynamic query into a database that returns a collection of records. The UDDL Query Language does not do
dynamic queries into a database. Instead, it statically defines the data you want to use. In essence, each query defines a slice of the available data that
you want to use, with all the relationships and cardinality from the original data model maintained. That defined data structure can then be used 
anywhere you need that data. The primary use of these defined slices is in APIs between components - one of those may be a DB - but that isn't required.
