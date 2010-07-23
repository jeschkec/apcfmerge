NAME
    apcfmerge - print the complete apache config, including include files

SYNOPSIS
    apcfmerge [OPTIONS] [ARGUMENTS]

        -h  --help      Print help
        -V  --version   Print version
            --stdin     Read from STDIN
            --no-stats  Print no statistics        
            --debug     Print debugging informations
            --httpd-conf=FILE
                        Read httpd.conf from FILE
            --server-root=PATH
                        Path to server root

OPTIONS
    --help, -h
        Print this help

    --version, -V
        Print version information

    --stdin, --si
        Read data from STDIN

    --no-stats
        Print no statistics after program execution

    --debug
        Print debugging information

ARGUMENTS
    --httpd-conf=httpd.conf
        Read the httpd configuration from httpd.conf.

    --server-root=server-root
        Set ServerRoot to server-root instead reading it from httpd
        configuration file.

EXAMPLES
      Assuming your httpd.conf file is located at /etc/apache/httpd.conf
      call the apcfmerge with the following parameters:

          apcfmerge --httpd-conf=/etc/apache/httpd.conf

      If, for any circumstances, your ServerRoot is not set or you want to
      override the settings invoke the apcfmerge with the following
      parameters (assuming, your server root is /srv/www)

          apcfmerge --httpd-conf=/etc/apache/httpd.conf --server-root=/srv/www

      If you want to read your httpd.conf from the standard input (i.e. by
      piping output to the apcfmerge), use the --stdin option:

          cat /etc/apache/httpd.conf | apcfmerge --stdin

      (This example is somewhat useless, because you can read the file
      directly and save your time from wasting it with cat and the slow
      pipe.)

SEE ALSO
    apachectl - for checking your apache configuration for syntax

INSTALL
    You need a couple of (CPAN) libraries to use this script:

    * Pod::Usage
    * Getopt::Long

VERSION
    apcfmerge
    Version 1.0.1
    Revision $Rev: 2 $,
    Date $Date: 2009-12-04 10:00:07 +0100 (Fr, 04 Dez 2009) $

BUGS AND LIMITATIONS
  Windows
    The apcfmerge is yet not tested with Windows, because the maintainer is
    currently refusing to use such a platform. If you can provide experience
    with this, please feel free to contact the maintainer.

  Circular includes
    In this current version, circular includes are not detected. A endless
    loop will be created.

  Contact
      Please report bugs to Christoph Jeschke <dev@christoph-jeschke.de>.

      Please set also your LC_MESSAGES to "C".

      Patches are welcome.

LICENSE AND COPYRIGHT
  COPYRIGHT
    apcfmerge - print the complete httpd config Copyright (c) 2009 Christoph
    Jeschke

  LICENSE
    This program is free software; you can redistribute it and/or modify it
    under the terms of the GNU General Public License as published by the
    Free Software Foundation; either version 2 of the License.

    This program is distributed in the hope that it will be useful, but
    WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General
    Public License for more details.

    You should have received a copy of the GNU General Public License along
    with this program; if not, write to the

    Free Software Foundation, Inc., 51 Franklin Street, Fifth Floor, Boston,
    MA 02110-1301 USA.

ACKNOWLEDGEMENTS
    Damian Conway
      For his book Perl Best Practices (O'Reilly, ISBN 0-596-00173-8)

