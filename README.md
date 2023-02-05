LOC-Extension: LibreOffice calc Cryptocurrency market functions
===

The LOC extension allows you to create customized spreadsheets with cryptocurrency market data directly from the web. 

Version 0.3.2 provides compatibility with LibreOffice 7.4

For the full documentation, see the original author's repo: [walkjivefly](https://github.com/walkjivefly/LOC-Extension)

### Download   
You can download the current version of the LOC Extension here:  [LOC.oxt](https://github.com/lbayle/LOC-Extension/blob/master/LOC.oxt)

**NOTE**: The extension itself is LOC.oxt
The example .ods worksheet demonstrates how to use the extension.

### Usage

The LOC-Extension adds five new functions to Calc.
The most interesting one is `CCXT`

```
CCXT(Exchange, Ticker, Datacode)
```

- ***Exchange*** is any exchange name supported by the system-installed version of ccxt.
- ***Ticker*** is a currency pair from the ccxt unified API.
- ***Datacode*** is one of the ccxt supported data items for the fetch_ticker function. The one you'll probably use most is "last".


The following formula will return the current price for "BTC/USDT":
`=COM.LOC.CRYPTO.GETINFO.PYTHON.LOCIMPL.CCXT("binance","BTC/USDT","last")`


### Compile on Manjaro Linux

1. Install Manjaro libreoffice packages
`libreoffice-fresh` &  `libreoffice-fresh-sdk`

2. Install ccxt on Manjaro by following [this tutorial](https://arch.pkgs.info/guide/complete-guide-on-python-ccxt-installation-on-arch-linux-manjaro-arcolinux)
```bash
sudo pacman -S --needed git && git clone https://aur.archlinux.org/python-ccxt.git && cd python-ccxt && makepkg -si
```

3. Compile LOC.oxt
```bash
git clone https://github.com/lbayle/LOC-Extension.git
cd LOC-Extension
./compile.sh
mv LOC.oxt LOC_0.3.2.oxt
```
4. upload & activate the plugin with the LibreOffice 'Extension manager' from the `Tools` menu



### Support

For general support please visit the author's [forums](http://forum.openoffice.org/en/forum/index.php). If you find a bug or wish to request a feature please file an issue at the [issue tracker](http://github.com/walkjivefly/LOC-Extension/issues).


### License

The `LOC Extension` is released under the [![][shield:LGPL3]][License:3.0]

`ccxt` is released under the MIT license.

### Warranty

There is **NO** warranty of any kind. You use the software entirely at your own risk. I am not responsible if anything goes wrong.

### Other Contributors and Thanks!
* walkjivefly - the original author of this plugin : [LOC-Extension](https://github.com/walkjivefly/LOC-Extension)
* madsailor - provided the original SMF Extension that LOC is based on
* Igor Kroitor - actively maintains the [ccxt](https://github.com/ccxt/ccxt) library


[GIT:release]: http://github.com/walkjivefly/LOC-Extension/releases/latest
[License:3.0]: http://www.gnu.org/licenses/lgpl.html
[shield:LGPL3]: http://img.shields.io/badge/license-LGPL%20v.3-blue.svg
