# Customized Portfiles for MacPorts

Some private customized Portfiles. Not tested.

## History

TODO: Write history

## Installation

*NOTE: You must have [MacPorts](https://www.macports.org/) installed.*

1. Download or clone this repository into your `$HOME` dir (it can be placed anywhere, as long as you use that path in the following instructions):

        cd $HOME
        git clone https://github.com/dsoares/portfiles.git

2. Now you need to tell MacPorts to look first for Portfiles in this local path.

    Manually edit the file `/opt/local/etc/macports/sources.conf` and insert a URL pointing to your local repository location before the rsync URL as shown:

        (...)
        file:///Users/<your_username>/portfiles [nosync]
        rsync://rsync.macports.org/release/tarballs/ports.tar [default]

    or use this command line to add the line to `/opt/local/etc/macports/sources.conf`:

        cd /opt/local/etc/macports
        cp -p sources.conf sources.conf.bak
        awk '/^rsync:/ && !x {print "file://'"$HOME"'/portfiles [nosync]"; x=1} 1' \
            sources.conf.bak > sources.conf
        cd -

3. Use `portindex` in the local repository's directory to create or update the index of the ports in your local repository:

        cd $HOME/portfiles
        portindex

## Usage

TODO: Write usage instructions.

- opencv: `sudo port install opencv-devel`


## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

## License

Released under the [GNU General Public License][gpl].

## Contact

Comments and suggestions are welcome!
Email: [Diana Soares][dsoares]

[![Flattr this git repo](http://api.flattr.com/button/flattr-badge-large.png)](https://flattr.com/submit/auto?user_id=dsoares&url=https://github.com/dsoares/portfiles&title=portfiles&language=&tags=github&category=software)



[gpl]: http://www.gnu.org/licenses/gpl.html
[dsoares]: mailto:diana.soares@gmail.com
