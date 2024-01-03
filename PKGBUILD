pkgname=ncloud-cli 
pkgver=1.1.17_20231123
pkgrel=1
pkgdesc="naver cloud cli"
arch=('any')
url="https://cli-fin.ncloud-docs.com/docs/guide-clichange"
license=('APACHE')
# TODO : JDK 1.8
# depends=()

source=("https://www.fin-ncloud.com/api/support/download/files/cli/FIN_CLI_$pkgver.zip"
        "ncloud-cli.sh")
sha256sums=('5c06e7870feb4a440100cb1468bfde976e965ebe10fd613e7e6af9e35b8d59c2'
            '527468f6aa092ae9cd81f380df0f960a018756d229056f585e4f47c028b4ce95')

package() {
    # Create directory structure
    mkdir -p $pkgdir/{etc/profile.d,opt}

    # Install path profile
    cp $pkgname.sh $pkgdir/etc/profile.d/

    # Install program files
    mv FIN_CLI_$pkgver/cli_linux $pkgdir/opt/$pkgname

    # "./" 를 "/opt/ncloud-cli" 로 변경
    sed -i 's/\.\//\/opt\/ncloud-cli\//g' $pkgdir/opt/$pkgname/ncloud

}
