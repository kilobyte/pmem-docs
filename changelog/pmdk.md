# PMDK Changelog

The master branch changelog in text format for the current development version can be found at [https://github.com/pmem/pmdk/blob/master/ChangeLog](https://github.com/pmem/pmdk/blob/master/ChangeLog)

### Conventions

This changelog uses the following conventions

* Each release has a publication date along with the name of the publisher
* Changes are prefixed with a tag denoting the area, if any, they relate to.  For example: 'doc' \(documentation\), 'obj' \(libpmemobj\), 'pool' \(libpmempool\), etc
* Bugs and new features may link to [PMDK issue repository](https://github.com/pmem/issues/issues) using '\(\#nnn\)' or external bug repositories such as the Red Hat Bugzilla \(RHBZ\).

## 

Thu Mar 29 2018 Krzysztof Czurylo &lt;krzysztof.czurylo@intel.com&gt;

This is the first release of PMDK under a new name.

### 

* common: support for concatenated Device-DAX devices
* common: add support for MAP\_SYNC flag
* common: always enable Valgrind instrumentation \([\#292](https://github.com/pmem/issues/issues/292)\)
* common: pool set options / headerless pools
* pmem: add support for "deep flush" operation
* rpmem: add rpmem\_deep\_persist
* doc: split man pages and add per-function aliases \([\#385](https://github.com/pmem/issues/issues/385)\)

### 

* pmem: skip CPU cache flushing when eADR is available
* pmem: add AVX512F support in pmem\_memcpy/memset \([\#656](https://github.com/pmem/issues/issues/656)\)

### Bug fixes

* common: fix library dependencies \([\#767](https://github.com/pmem/issues/issues/767), [RHBZ \#1539564](https://bugzilla.redhat.com/show_bug.cgi?id=1539564)\)
* common: use rpm-config CFLAGS/LDFLAGS when building packages
* common: do not unload librpmem on close \([\#776](https://github.com/pmem/issues/issues/776)\)
* common: fix NULL check in os\_fopen \([\#813](https://github.com/pmem/issues/issues/813)\)
* common: fix missing version in .pc files
* obj: fix cancel of huge allocations \([\#726](https://github.com/pmem/issues/issues/762)\)
* obj: fix error handling in pmemobj\_open \([\#750](https://github.com/pmem/issues/issues/750)\)
* obj: validate pe\_offset in pmemobj\_list\_\* APIs \([\#772](https://github.com/pmem/issues/issues/772)\)
* obj: fix add\_range with size == 0 \([\#781](https://github.com/pmem/issues/issues/781)\)
* log: add check for negative iovcnt \([\#690](https://github.com/pmem/issues/issues/690)\)
* rpmem: limit maximum number of lanes \([\#609](https://github.com/pmem/issues/issues/609)\)
* rpmem: change order of memory registration \([\#655](https://github.com/pmem/issues/issues/655)\)
* rpmem: fix removing remote pools \([\#721](https://github.com/pmem/issues/issues/721)\)
* pool: fix error handling \([\#643](https://github.com/pmem/issues/issues/643)\)
* pool: fix sync with switched parts \([\#730](https://github.com/pmem/issues/issues/730)\)
* pool: fix sync with missing replica \([\#731](https://github.com/pmem/issues/issues/731)\)
* pool: fix detection of Device DAX size \([\#805](https://github.com/pmem/issues/issues/805)\)
* pool: fail pmempool\_sync if there are no replicas \([\#816](https://github.com/pmem/issues/issues/816)\)
* benchmark: fix calculating standard deviation \([\#318](https://github.com/pmem/issues/issues/318)\)
* doc: clarify pmem\_is\_pmem behavior \([\#719](https://github.com/pmem/issues/issues/719)\)
* doc: clarify pmemobj\_root behavior \([\#733](https://github.com/pmem/issues/issues/733)\)

### 

* common: port PMDK to FreeBSD
* common: add experimental support for aarch64
* obj: introduce allocation classes
* obj: introduce two-phase heap ops \(reserve/publish\) \([\#380](https://github.com/pmem/issues/issues/380), [\#415](https://github.com/pmem/issues/issues/415)\)
* obj: provide basic heap statistics \([\#676](https://github.com/pmem/issues/issues/676)\)
* obj: implement run-time pool extending \([\#382](https://github.com/pmem/issues/issues/382)\)
* cto: add close-to-open persistence library \([\#192](https://github.com/pmem/issues/issues/192)\)

### 

The following features are disabled by default, until

* daxio: add utility to perform I/O on Device-DAX
* RAS: unsafe shutdown detection/handling

## 

Wed Dec 20 2017 Krzysztof Czurylo &lt;krzysztof.czurylo@intel.com&gt;

### Bug fixes

* rpmem: fix issues reported by Coverity
* rpmem: fix read error handling
*  rpmem: add fip monitor \([\#597](https://github.com/pmem/issues/issues/597)\)
* test: add rpmemd termination handling test
* cpp: fix pop.persist function in obj\_cpp\_ptr
* rpmem: return failure for a failed allocation
* rpmem: fix potential memory leak
* common: fix available rm options msg \([\#651](https://github.com/pmem/issues/issues/651)\)
* pool: fix pmempool\_get\_max\_size
* obj: fix potential deadlock during realloc \([\#635](https://github.com/pmem/issues/issues/635), [\#636](https://github.com/pmem/issues/issues/636), [\#637](https://github.com/pmem/issues/issues/637)\)
* obj: initialize TLS data
* rpmem: fix cleanup if fork\(\) failed \([\#634](https://github.com/pmem/issues/issues/634)\)
* obj: fix bogus OOM after exhausting first zone

## Version 1.3

Thu Jul 13 2017 Krzysztof Czurylo &lt;krzysztof.czurylo@intel.com&gt;

This release introduces some useful features and optimizations





### 

* common: add support for concatenated DAX Devices
* common: add Unicode support on Windows
* common: add long path support on Windows
* common: add NVML installer for Windows
* pmem: make pmem\_is\_pmem\(\) true for Device DAX only
* obj: add pmemobj\_wcsdup\(\)/pmemobj\_tx\_wcsdup\(\) APIs
* obj: export non-inlined pmemobj\_direct\(\)
* obj: add PMEMOBJ\_NLANES env variable
* cpp: introduce the allocator
* cpp: add wstring version of C++ entry points
* vmem: add vmem\_wcsdup\(\) API entry
* pool: add pmempool\_rm\(\) function \([\#307](https://github.com/pmem/issues/issues/307)\)
* pool: add --force flag for create command \([\#529](https://github.com/pmem/issues/issues/529)\)
* benchmark: add a minimal execution time option
* benchmark: add thread affinity option
* benchmark: print 99% and 99.9% percentiles
* doc: separate Linux/Windows version of web-based man pages

### Optimizations:

* obj: cache \_pobj\_cached\_pool in pmemobj\_direct\(\)
* obj: optimize thread utilization of buckets
* obj: stop grabbing a lock when querying pool ptr
* rpmem: use multiple endpoints

### 

* common: fix issues reported by static code analyzers
* pmem: fix mmap\(\) implementation on Windows
* pmem: fix mapping addr/length alignment on Windows
* pmem: fix PMEM\_MMAP\_HINT implementation on Windows
* pmem: fix pmem\_is\_pmem\(\) on invalid memory ranges
* pmem: fix wrong is\_pmem returned by pmem\_map\_file\(\)
* pmem: fix mprotect\(\) for private mappings on Windows
* pmem: modify pmem\_is\_pmem\(\) behavior for len==0
* obj: add failsafe to prevent allocs in constructor
* cpp: fix swap implementation
* cpp: fix sync primitives' constructors
* cpp: fix wrong pointer type in the allocator
* cpp: return persistent\_ptr::swap to being public
* pool: treat invalid answer as 'n'
* pool: unify flags value for dry run
* pool: transform for remote replicas
* rpmem: persistency method detection
* benchmark: fix time measurement

### Experimental features & optimizations

* obj: pmemobjctl - statistics and control submodule \([\#194](https://github.com/pmem/issues/issues/194), [\#211](https://github.com/pmem/issues/issues/211)\)
* obj: zero-overhead allocations - customizable alloc header \([\#347](https://github.com/pmem/issues/issues/347)\)
* obj: flexible run size index \([\#377](https://github.com/pmem/issues/issues/377)\)
* obj: dynamic range cache \([\#378](https://github.com/pmem/issues/issues/378)\)
* obj: asynchronous post-commit \([\#381](https://github.com/pmem/issues/issues/381)\)
* obj: configurable object cache \([\#515](https://github.com/pmem/issues/issues/515)\)
* obj: add cache size and threshold tx params
* obj: add CTL var for suppressing expensive checks
* rpmem: add rpmem\_set\_attr\(\) API entry
* rpmem: switch to libfabric v1.4.2

## Version 1.2.3

Thu May 18 2017 Krzysztof Czurylo &lt;krzysztof.czurylo@intel.com&gt;

### Bug fixes

* test: extend timeout for selected tests
* test: reduce number of operations in obj\_tx\_mt
* test: define cfree\(\) as free\(\) in vmmalloc\_calloc

### Other changes:

* common: move Docker images to new repo

## Version 1.2.2

Sat Apr 15 2017 Krzysztof Czurylo &lt;krzysztof.czurylo@intel.com&gt;

### Bug fixes

* pmempool: fix mapping type in pool\_params\_parse
* test: limit number of arenas in vmem\_stats
* test: do not run pool\_lock test as root
* common: fix pkg-config files
* common: fix building packages for Debian

## Version 1.2.1

Tue Feb 21 2017 Krzysztof Czurylo &lt;krzysztof.czurylo@intel.com&gt;



### Bug fixes:

* jemalloc: fix test compilation on Fedora 26 \(rawhide\)
* test: fix cpp test compilation on Fedora 26 \(rawhide\)
* common: use same queue.h on linux and windows
* common: queue.h clang static analyzer fix
* common: fix path handling in build-dpkg.sh
* test: fix match files in pmempool\_transform/TEST8

## 

Fri Dec 30 2016 Krzysztof Czurylo &lt;krzysztof.czurylo@intel.com&gt;





### New Windows Support



* win: port libvmem \(and jemalloc\)
* win: benchmarks Windows port
* win: fix mapping files of unaligned length
* win: clean up possible race condition in mmap\_init\(\)
* win: enable QueryVirtualMemoryInformation\(\) in pmem\_is\_pmem\(\)
* test: check open handles at START/DONE
* test: port all the remaining unit tests
* win: add resource files for versioning

### Known Issues

Known issues and limitations of Windows version of NVML:

* Unicode support is missing.  The UTF/USC-encoded file paths
* The libvmmalloc library is not ported yet.
* The on-media format of pmem pools is not portable at the moment.
* The pmem pools created using Windows version of NVM libraries
* Despite the fact the current version of NVML would work

## 

Thu Dec 15 2016 Krzysztof Czurylo &lt;krzysztof.czurylo@intel.com&gt;



The major version number of the pmemobj pool layout and the version

### Key Changes

* Add Device DAX support, providing that "optimized flush" mechanism
* Add a package for libpmemobj C++ bindings.
* C++ API is no longer considered experimental.
* Web-based documentation for C++ API is available on http://pmem.io.
* Add "sync" and "transform" commands to pmempool utility.
* Add experimental support for remote access to persistent memory and

### New features

* common: add Device DAX support \([\#197](https://github.com/pmem/issues/issues/197)\)
* obj: add C++ bindings package \(libpmemobj++-devel\)
* obj: add TOID\_OFFSETOF macro
* pmempool: add "sync" and "transform" commands \([\#172](https://github.com/pmem/issues/issues/172), [\#196](https://github.com/pmem/issues/issues/196)\)

### Bug fixes

* obj: force alignment of pmem lock structures \([\#358](https://github.com/pmem/issues/issues/358)\)
* blk: cast translation entry to uint64\_t when calculating data offset
* obj: fix Valgrind instrumentation of chunk headers and cancelled
* obj: set error message when user called pmemobj\_tx\_abort\(\)
* obj: fix status returned by pmemobj\_list\_insert\(\) \([\#226](https://github.com/pmem/issues/issues/226)\)
* obj: defer allocation of global structures

### Optimizations

* obj: fast path for pmemobj\_pool\_by\_ptr\(\) when inside a transaction
* obj: simplify and optimize allocation class generation

### 

* rpmem: add support for remote access to persistent memory and basic
* libpmempool: add pmempool\_sync\(\) and pmempool\_transform\(\) \([\#196](https://github.com/pmem/issues/issues/196)\)
* obj: introduce pmemobj\_oid\(\)
* obj: add pmemobj\_tx\_xalloc\(\)/pmemobj\_tx\_xadd\_range\(\) APIs and
* obj: add transaction stage transition callbacks

## Version 1.1

Thu Jun 23 2016 Krzysztof Czurylo &lt;krzysztof.czurylo@intel.com&gt;



Internal undo log structure has been modified to improve performance



### 

* pmem: deprecate PCOMMIT
* blk: match BTT Flog initialization with Linux NVDIMM BTT
* mem: defer pmem\_is\_pmem\(\) initialization \([\#158](https://github.com/pmem/issues/issues/158)\)
* obj: add TOID\_TYPEOF macro

### 

* doc: update description of valid file size units \([\#133](https://github.com/pmem/issues/issues/133)\)
* pmempool: fix --version short option in man page \([\#135](https://github.com/pmem/issues/issues/135)\)
* pmempool: print usage when running rm without arg \([\#136](https://github.com/pmem/issues/issues/136)\)
* cpp: clarify polymorphism in persistent\_ptr \([\#150](https://github.com/pmem/issues/issues/150)\)
* obj: let the before flag be any non-zero value \([\#151](https://github.com/pmem/issues/issues/151)\)
* obj: fix compare array pptr to nullptr \([\#152](https://github.com/pmem/issues/issues/152)\)
* obj: cpp pool.get\_root\(\) fix \([\#156](https://github.com/pmem/issues/issues/156)\)
* log/blk: set errno if replica section is specified \([\#161](https://github.com/pmem/issues/issues/161)\)
* cpp: change exception message \([\#163](https://github.com/pmem/issues/issues/163)\)
* doc: remove duplicated words in man page \([\#164](https://github.com/pmem/issues/issues/164)\)
* common: always append EXTRA\_CFLAGS after our CFLAGS

### 

* Implementation of C++ bindings for libpmempobj is complete.
* Web-based documentation for C++ API is available on http://pmem.io.
* Porting NVML to Windows is in progress.  There are MS Visual Studio

## Version 1.0

Thu Apr 07 2016 Krzysztof Czurylo &lt;krzysztof.czurylo@intel.com&gt;

The API of six libraries \(libpmem, libpmemblk, libpmemlog,

The on-media layout of persistent memory pools will be maintained

Man pages are all complete.

This release has been validated to "Production quality".

For the purpose of new features planned for next releases of NVML

* pmem: pmem\_map replaced with pmem\_map\_file
* log/blk: 'off\_t' substituted with 'long long'
* obj: type numbers extended to 64-bit
* obj: new entry points and macros added:
  * pmemobj\_tx\_errno
  * pmemobj\_tx\_lock
  * pmemobj\_mutex\_timedlock,
  * TX\_ADD\_DIRECT
  * TX\_ADD\_FIELD\_DIRECT
  * TX\_SET\_DIRECT



* common: updated/fixed installation scripts
* common: eliminated dependency on libuuid
* pmem: CPU features/ISA detection using CPUID
* obj: improved error handling
* obj: atomic allocation fails if constructor returns error
* obj: multiple performance optimizations
* obj: object store refactoring
* obj: additional examples and benchmarks



## 

Fri Dec 04 2015 Krzysztof Czurylo &lt;krzysztof.czurylo@intel.com&gt;



* benchmarks for libpmemobj, libpmemblk and libvmem
* additional pmemobj tests and examples
* pool mapping address randomization
* added pmempool "rm" command
* eliminated libpmem dependency on libpthread
* enabled extra warnings
* minor performance improvements

Man pages are all complete.

This release is considered "Beta quality" by the team, having

The pmempool command does not yet support "check" and "repair"

## 

Sun Sep 13 2015 Andy Rudoff &lt;andy.rudoff@intel.com&gt;

NVML is now feature complete, adding support for:

* pool sets
* pmemobj local replication \(active/passive\)
* experimental valgrind support
* pmempool support for all pool types

Man pages are all complete.

This release is considered "Alpha quality" by the team, having

## 

Tue Jun 30 2015 Andy Rudoff &lt;andy.rudoff@intel.com&gt;

NVML now consists of six libraries:

* libpmem  \(basic flushing, etc\)
* libpmemblk, libpmemlog, libpmemobj \(transactions\)
* libvmem, libvmmalloc  \(volatile use of pmem\)

The "pmempool" command is available for managing pmem files.

Man pages for all the above are complete.

The only things documented in man pages but not implemented are:

* pmem sets \(ability to spread a pool over a set of files\)
* replication \(coming for libpmemobj\)

The pmempool command does not yet support pmemobj type pools.

## 

Thu Sep 11 2014 Andy Rudoff &lt;andy.rudoff@intel.com&gt;

* Initial development done in 0.1 builds
