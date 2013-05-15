BioPerl
=======

Local install

INSTALLING IN A PERSONAL MODULE AREA
If you lack permission to install perl modules into the standard site_perl/ system area you can configure BioPerl to install itself anywhere you choose. This could be a personal perl directory or a standard place where you plan to put all your 'local' or personal perl modules.
Simply pass a parameter to perl as it builds your system specific makefile.

Example:
>perl Build.PL --install_base /home/users/dag
>./Build test
>./Build install

This tells perl to install all the various parts of bioperl in the desired place, e.g. creating:

/home/users/dag/lib/perl5/Bio/

Then in your Bioperl script you would write:
use lib "/home/users/dag/lib/perl5/";
use Bio::Perl;
