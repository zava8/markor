#!/usr/bin/perl
#rename 's/txt$/html/' *
#rename 's/new$/old/' mah*.new
#rename 's/(.+)/\.$1/' *
# Usage: rename perlexpr [files]
($regexp = shift @ARGV) || die "Usage:  rename perlexpr [filenames] ";
if (!@ARGV) {

   @ARGV = <STDIN>;
   chomp(@ARGV);
}
foreach $_ (@ARGV) {
   $old_name = $_;
   eval $regexp;
   die $@ if $@;
   rename($old_name, $_) unless $old_name eq $_;
}
exit(0);
