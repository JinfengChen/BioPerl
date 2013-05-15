BioPerl
=======

Local install

INSTALLING IN A PERSONAL MODULE AREA
If you lack permission to install perl modules into the standard site_perl/ system area you can configure BioPerl to install itself anywhere you choose. This could be a personal perl directory or a standard place where you plan to put all your 'local' or personal perl modules.
Simply pass a parameter to perl as it builds your system specific makefile.

Example:

Install bioperl
>wget http://search.cpan.org/CPAN/authors/id/C/CJ/CJFIELDS/BioPerl-1.6.901.tar.gz
>uz BioPerl-1.6.901.tar.gz
>cd BioPerl-1.6.901/
>perl Build.PL --install_base /rhome/cjinfeng/software/tools/BioPerl
>./Build install
>export PERL5LIB=/rhome/cjinfeng/software/tools/BioPerl/lib/perl5:$PERL5LIB

Install bioperl package 
>wget http://search.cpan.org/CPAN/authors/id/L/LD/LDS/Bio-SamTools-1.37.tar.gz
>uz Bio-SamTools-1.37.tar.gz
>cd Bio-SamTools-1.37/
>

This tells perl to install all the various parts of bioperl in the desired place, e.g. creating:

>/home/users/dag/lib/perl5/Bio/

Then in your Bioperl script you would write:

>use lib "/home/users/dag/lib/perl5/";
>use Bio::Perl;
