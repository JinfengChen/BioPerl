BioPerl
=======

Local install

INSTALLING IN A PERSONAL MODULE AREA
If you lack permission to install perl modules into the standard site_perl/ system area you can configure BioPerl to install itself anywhere you choose. This could be a personal perl directory or a standard place where you plan to put all your 'local' or personal perl modules.
Simply pass a parameter to perl as it builds your system specific makefile.

Example:

Install bioperl
>wget http://search.cpan.org/CPAN/authors/id/C/CJ/CJFIELDS/BioPerl-1.6.901.tar.gz;

>uz BioPerl-1.6.901.tar.gz;

>cd BioPerl-1.6.901/;

>perl Build.PL --install_base /rhome/cjinfeng/software/tools/BioPerl;

>./Build install;

>export PERL5LIB=/rhome/cjinfeng/software/tools/BioPerl/lib/perl5:$PERL5LIB;

Install bioperl package "Bio-SamTools" 

Before install
1. When building this module, you get an error like the following:
relocation R_X86_64_32 against `a local symbol' can not be used when
making a shared object; recompile with -fPIC

To fix this, edit the Makefile in the Samtools distribution by adding
"-fPIC" to the CFLAGS line. It should look like this:

  CFLAGS=  -g -Wall -O2 -fPIC #-m64 #-arch ppc

2. Use samtools-0.1.6

>wget http://search.cpan.org/CPAN/authors/id/L/LD/LDS/Bio-SamTools-1.37.tar.gz

>uz Bio-SamTools-1.37.tar.gz

>cd Bio-SamTools-1.37/

>perl Build.PL --install_base /rhome/cjinfeng/software/tools/Perl_lib

>./Build

>./Build test

>./Build install

>perl Makefile.PL PREFIX=/rhome/cjinfeng/software/tools/Perl_lib

>make 

>make test

>make install

>export PERL5LIB=/rhome/cjinfeng/software/tools/Perl_lib/lib/perl5/x86_64-linux-gnu-thread-multi:$PERL5LIB

