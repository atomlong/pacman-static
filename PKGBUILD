# Maintainer: Eli Schwartz <eschwartz@archlinux.org>

# All my PKGBUILDs are managed at https://github.com/eli-schwartz/pkgbuilds

pkgname=pacman-static
pkgver=6.0.2
_cares_ver=1.19.1
_nghttp2_ver=1.56.0
_curlver=8.3.0
_sslver=3.1.3
_zlibver=1.3
_xzver=5.4.4
_bzipver=1.0.8
_zstdver=1.5.5
_libarchive_ver=3.7.2
_gpgerrorver=1.47
_libassuanver=2.5.6
_gpgmever=1.22.0
pkgrel=6
pkgdesc="Statically-compiled pacman (to fix or install systems without libc)"
arch=('i486' 'i686' 'pentium4' 'x86_64' 'arm' 'armv6h' 'armv7h' 'aarch64')
url="https://www.archlinux.org/pacman/"
license=('GPL')
depends=('pacman')
makedepends=('meson' 'musl' 'kernel-headers-musl')
options=('!emptydirs')

# pacman
source=("https://sources.archlinux.org/other/pacman/pacman-${pkgver}.tar.xz"{,.sig}
        pacman-always-create-directories-from-debugedit.patch::https://gitlab.archlinux.org/pacman/pacman/-/commit/efd0c24c07b86be014a4edb5a8ece021b87e3900.patch
        pacman-always-create-directories-from-debugedit-fixup.patch::https://gitlab.archlinux.org/pacman/pacman/-/commit/86981383a2f4380bda26311831be94cdc743649b.patch
        pacman-fix-unique-source-paths.patch::https://gitlab.archlinux.org/pacman/pacman/-/commit/478af273dfe24ded197ec54ae977ddc3719d74a0.patch
        pacman-strip-include-o-files-similar-to-kernel-modules.patch::https://gitlab.archlinux.org/pacman/pacman/-/commit/de11824527ec4e2561e161ac40a5714ec943543c.patch
        pacman-fix-compatibility-with-bash-5.2-patsub_replacement.patch::https://gitlab.archlinux.org/pacman/pacman/-/commit/0e938f188692c710be36f9dd9ea7b94381aed1b4.patch
        pacman-fix-order-of-fakechroot-fakeroot-nesting.patch::https://gitlab.archlinux.org/pacman/pacman/-/commit/05f283b5ad8f5b8f995076e93a27c8772076f872.patch)

validpgpkeys=('6645B0A8C7005E78DB1D7864F99FFE0FEAE999BD'  # Allan McRae <allan@archlinux.org>
              'B8151B117037781095514CA7BBDFFC92306B1121') # Andrew Gregory (pacman) <andrew@archlinux.org>
# nghttp2
source+=("https://github.com/nghttp2/nghttp2/releases/download/v$_nghttp2_ver/nghttp2-$_nghttp2_ver.tar.xz")
# c-ares
source+=("https://c-ares.haxx.se/download/c-ares-${_cares_ver}.tar.gz"{,.asc})
validpgpkeys+=('27EDEAF22F3ABCEB50DB9A125CC908FDB71E12C2') # Daniel Stenberg <daniel@haxx.se>
# curl
source+=("https://curl.haxx.se/download/curl-${_curlver}.tar.gz"{,.asc})
validpgpkeys+=('27EDEAF22F3ABCEB50DB9A125CC908FDB71E12C2') # Daniel Stenberg
# openssl
source+=("https://www.openssl.org/source/openssl-${_sslver}.tar.gz"{,.asc}
         "ca-dir.patch"
         "openssl-3.0.7-no-atomic.patch")
validpgpkeys+=('8657ABB260F056B1E5190839D9C4D26D0E604491'
              '7953AC1FBC3DC8B3B292393ED5E9E43F7DF9EE8C'
              'A21FAB74B0088AA361152586B8EF1A6BA9DA2D5C'
              'EFC0A467D613CB83C7ED6D30D894E2CE8B3D79F5')

validpgpkeys+=('8657ABB260F056B1E5190839D9C4D26D0E604491'  # Matt Caswell <matt@openssl.org>
              '7953AC1FBC3DC8B3B292393ED5E9E43F7DF9EE8C'   # Matt Caswell <matt@openssl.org>
              'A21FAB74B0088AA361152586B8EF1A6BA9DA2D5C'   # Tom�? Mr�z <tm@t8m.info>
              'EFC0A467D613CB83C7ED6D30D894E2CE8B3D79F5')  # OpenSSL security team key
# zlib
source+=("https://zlib.net/zlib-${_zlibver}.tar.gz"{,.asc})
validpgpkeys+=('5ED46A6721D365587791E2AA783FCD8E58BCAFBA') # Mark Adler <madler@alumni.caltech.edu>
# xz
source+=("https://tukaani.org/xz/xz-${_xzver}.tar.gz"{,.sig})
validpgpkeys+=('3690C240CE51B4670D30AD1C38EE757D69184620'  # Lasse Collin <lasse.collin@tukaani.org>
              '22D465F2B4C173803B20C6DE59FCF207FEA7F445') # Jia Tan <jiat0218@gmail.com>
# bzip2
source+=("https://sourceware.org/pub/bzip2/bzip2-${_bzipver}.tar.gz"{,.sig})
validpgpkeys+=('EC3CFE88F6CA0788774F5C1D1AA44BE649DE760A') # Mark Wielaard <mark@klomp.org>
# zstd
source+=("https://github.com/facebook/zstd/releases/download/v${_zstdver}/zstd-${_zstdver}.tar.zst"{,.sig})
validpgpkeys+=('4EF4AC63455FC9F4545D9B7DEF8FE99528B52FFD') # Zstandard Release Signing Key <signing@zstd.net>
# libgpg-error
source+=("https://gnupg.org/ftp/gcrypt/libgpg-error/libgpg-error-${_gpgerrorver}.tar.bz2"{,.sig})
validpgpkeys+=('D8692123C4065DEA5E0F3AB5249B39D24F25E3B6'  # Werner Koch
               '031EC2536E580D8EA286A9F22071B08A33BD3F06'  # NIIBE Yutaka (GnuPG Release Key) <gniibe@fsij.org>
               '6DAA6E64A76D2840571B4902528897B826403ADA') # "Werner Koch (dist signing 2020)"
# libassuan
source+=("https://gnupg.org/ftp/gcrypt/libassuan/libassuan-${_libassuanver}.tar.bz2"{,.sig})
# gpgme
source+=("https://www.gnupg.org/ftp/gcrypt/gpgme/gpgme-${_gpgmever}.tar.bz2"{,.sig})
validpgpkeys+=('AC8E115BF73E2D8D47FA9908E98E9B2D19C6C8BD') #  Niibe Yutaka (GnuPG Release Key)
# libarchive
source+=("https://github.com/libarchive/libarchive/releases/download/v${_libarchive_ver}/libarchive-${_libarchive_ver}.tar.xz"{,.asc})
validpgpkeys+=('A5A45B12AD92D964B89EEE2DEC560C81CEC2276E'  # Martin Matuska <mm@FreeBSD.org>
              'DB2C7CF1B4C265FAEF56E3FC5848A18B8F14184B') # Martin Matuska <martin@matuska.org>

sha512sums=('9d76fb58c3a50e89a4b92b1f9e3bfdecca3f69e05022ea88fbd34f9df540c4fc688ad4f8b27e77eedb791aa682c27037abe65c789c6d9ee393bae5b620c3df13'
            'SKIP'
            'cb9e16c231ddbc4d296642941b58cbdd9e76d3f49e53e118819047917550373e44444575af593c02018beededbfa9d7e8a93a14859be43c630b18701ec8bab28'
            '67f28a6da5e4852c291e0a2e4c6ccce358e961ebe5e8a8cb7277322512ad08815efcbe09f9310cc4ea021900aaae65a9fcf56f5e51cd1fb8af99a06fc962aceb'
            'eea39274ca3935a7bc45c81eb9d5dd72f816cd8c7260b77a3a4fd9cdbcdd7643166d643628fd583d987218cadf4fa90ac394947d8aae8af84e1b69d2d3533e45'
            'ddd217c235c375e59e130a21aefeb531a3f6624f4e3937de75370d42c39063b2e14196e2d7fcbaa1745c93fd31454793dda031132e299f08aae6cf7b89d5d6fc'
            '8b0ab45c1bb6bd8da0c7e31c2c880fb74c8cbfe03c68ea3c9022fed6028d46b4a4ce94aaf158218576df9dcb01922c984cc29aa43469fafad15322f83bd82a29'
            '4c76fcd3472dea62772155ec0c2ecd49270a4717a3f06964836f4d575378f42ef71b2176f14f1693f15476c85081d593c072108915968467005aa0ff7a1c6741'
            '9754bd637705400cc4c3488d6dd1fc217c765a0925d2a5edfd83d380db0ad9e9a05974afa4fcda40b07287e8e8261b9d8009892cb1c2cc417ce4232a01b0011d'
            '466a94efda626e815a6ef7a890637056339f883d549ea6055e289fd8cd2391130e5682c905c0fb3bd7e955af7f6deb793562c170eb0ee066a4a62085a82ba470'
            'SKIP'
            '838f96b6faee949ae70060420d1cc31f3eb018160aaebef53acc850d9cd6d68cf15bf5d76e2838474aff05cb7f51b054bbada09a6257c60ff9892852bdc1da41'
            'SKIP'
            '2388eaa8e99acf1e8af4691a645b9b9af456900c74959e82d4cb02808301e11dcfecc86954a922262b16fa4b664b459894d133ab7d35ec82e1633a33194b7b20'
            'SKIP'
            'b1873dbb7a49460b007255689102062756972de5cc2d38b12cc9f389b6be412da6797579b1acd3717a8cd2ee118fd9801b94e55f063d4328f050f0876a5eb53c'
            'b5887ea77417fae49b6cb1e9fa782d3021f268d5219701d87a092235964f73fa72a31428b630445517f56f2bb69dcbbb24119ef9dbf8b4e40a753369a9f9a16f'
            '185795044461cd78a5545250e06f6efdb0556e8d1bfe44e657b509dd6f00ba8892c8eb3febe65f79ee0b192d6af857f0e0055326d33a881449f3833f92e5f8fb'
            'SKIP'
            '2e27d864c9f346e53afc549d7046385b5d35a749af15d84f69de14612657df2f0e2ce71d3be03d57adadf8fd28549ecf4ef1c214bdcd1f061b5a47239e0104e8'
            'SKIP'
            '083f5e675d73f3233c7930ebe20425a533feedeaaa9d8cc86831312a6581cefbe6ed0d08d2fa89be81082f2a5abdabca8b3c080bf97218a1bd59dc118a30b9f3'
            'SKIP'
            'c2d88b2c2050262f85be32877142c94e36a8ee451890f579cd2426c7de565fb22d21c369bad11f306093f0b356e935cef5a8ff5a2b0c007ade0f7e7eb944d2a5'
            'SKIP'
            'bbb4b15dae75856ee5b1253568674b56ad155524ae29a075cb5b0a7e74c4af685131775c3ea2226fff2f84ef80855e77aa661645d002b490a795c7ae57b66a30'
            'SKIP'
            'dcca942d222a2c226a7e34ba7988ee0c3c55bd6032166eb472caf2053db89aeeea7a40e93d8c2887c7ee73c5f838e8b0725e8cfb595accc1606646559362f7ee'
            'SKIP'
            '17053053fa885f01416433e43072ac716b5d5db0c3edf45b2d6e90e6384d127626e6ae3ce421abba8f449f5ca7e8963f3d62f3565d295847170bc998d1ec1a70'
            'SKIP'
            'a21bebb27b808cb7d2ed13a70739904a1b7b55661d8dea83c9897a0129cf71e20c962f13666c571782ff0f4f753ca885619c2097d9e7691c2dee4e6e4b9a2971'
            'SKIP')
b2sums=('648f62307e413cb352ed92e92df1ace510c1fc5e9ddd254baeef071e89cb7dae1786a95d29c5f69e8b03b1a8cfe3cd65671588dc362c8d3b281c092393aad54c'
        'SKIP'
        'b916ed6aa7deb1091b204d09187a3d9006c74976725ba81027841885276f2261415db7688359910ee8cbfd696e8dc310560cfbad2d3c0d88ad263425a6e1aa82'
        '8f781728405ae2590302171d0e6b0d723b00861e3a37be6678d8ad40e91217b513241a19a2a9912260ad0ec699eeb53b7c59aaa6c27f2c22cbb9443556bbf9de'
        'bb41ad66821bb5499825a7411b0ce8001092106d1dfc6d3b5ae10e1da8bc269e1775883520154496a2dc833fffaf11032466ecbadc123365eb2e6fa48bba4f3e'
        '64e042cbac411b323038504f843fcf786689a0b6d63b2d8ea5bb3431998dae1e98656923ac96b5ec99c03494aaab1ad8f60d2614b03947df5f607c43411060da'
        'ce420c696f4a8b4f3f64b4e9c4cdef0ea0225900145f10834314fcc8c371f84352453bd4c6c613f979f81d14453732c248a2a225c4bf5e2c678c9548ced11b31'
        '0dcdefcc7b4c15a408712c50b6371b76197a577d5069501225b8815c401fda8a40d897b51afe8f93ff54d0f1ac7f2a9054f016c5e5cb25d5cc2fe89b3819977b'
        'bb8270a636852a1c542d683feba7c55be74808ac17f6ac6774d4122a74d8d1fa4821234fa945b4c12aabf7bd7b608e70b45f729e5c7cd03cfebf8e285e419734'
        '4b6c9593edb1a91ab76d54ddacb1cd5d67006d5e628ea1f3289f54e9360be32abeb5d8fc7d23e193feab3e7928e8efde82757eb12fe217dc92ed0d9132bedf5d'
        'SKIP'
        '513caa9bc548fcb8d664b221e555df3e1a6457a856d4e787a28544d15c6f528b31ae57932b43bce1e3cf1e67faebe7de6c68eeeef73b1e124fab17f71c8d1ffa'
        'SKIP'
        'a279a5c80191b95ca735aed20beb56ab899ee302258ce3529c377820739bf55075537cd900b06b3ca07b85efdce95cb081bcad1dfd4d33f81695c7ef0cefdf03'
        'SKIP'
        '928c0cb15cca44bb7f194db9f95985f6c50aacd3e22fe2eb60ece26ed76469289f10d303c645a48407f3d6435ac66f25dd3c4cbc56fdc5dfd9ea2566feda9ff8'
        'c72172cf57389718b4722c3482ddaf9c2fc02aafe391c68edeb92d41fd6345a0a98f6fd63ddf01b33fe59a7a3f270ff1ccad432feba578b7b7e0170cd1dea7ef'
        '7dd64103163363f5e1fba57d2e436342768d1b702154a261185eb7eda42c51c17fb2b44c58381050d7e42d4a8ddb9817be78a8fd6291d1c40fbc45436d3feacd'
        'SKIP'
        '0ade3767651a07a6bb4d53b510d7e97239e182788c42bc3388b97c54463ccaa968e27bcb88d34697df70381eea91279615f2622b5493ae2da22632e9576d8989'
        'SKIP'
        '22ab3acd84f4db8c3d6f59340c252faedfd4447cea00dafbd652e65b6cf8a20adf6835c22e58563004cfafdb15348c924996230b4b23cae42da5e25eeac4bdad'
        'SKIP'
        '2c2dc95f227e661ada23d8f6141bcd293505ce14e605f946ae00d4d4ac37d10b4eb08279ef7560618c67caf266431f76686fda5ae1921d698a6a93bbaf9a0052'
        'SKIP'
        'bc04efa0686b1b7d7cdce045fc080c090c1abec60349b673c2e1ce27900483aea090eb6ebcb3fb49a4eed36f18156a12413d5446f739475632f4ed2a2481ff27'
        'SKIP'
        '462af1eab69e157f65f8134a492cde01dd1e0ee00609f2c2585e742fb9c5532b3fd96054b4fb7449e305690f70aa7a120085db42e2de2e3b0ef8b1603e7e5846'
        'SKIP'
        '6c03f4252391a114233fed284bf9eba03fa7b67328b506c01554fbd4239e0f3ede0bc79d82e9f21718084ca17945d628707d4451ac765a8f36d282e7e2d75f8e'
        'SKIP'
        '7221db4811a965ee61d879a2603480363628a19995a351b572d099be9f35576d76f0b0822f9a5a47d9929bc094d4444fd8eafcb4a073e39bb3aa797d4b926ca5'
        'SKIP')

export LDFLAGS="$LDFLAGS -static"
export CC=musl-gcc
export CXX=musl-gcc

# https://www.openwall.com/lists/musl/2014/11/05/3
# fstack-protector and musl do not get along but only on i686
if [[ $CARCH = i686 || $CARCH = pentium4 || $CARCH = i486 ]]; then
    # silly build systems have configure checks or buildtime programs that don't CFLAGS but do do CC
    export CC="musl-gcc -fno-stack-protector"
    export CXX="musl-gcc -fno-stack-protector"
    export CFLAGS="${CFLAGS/-fstack-protector-strong/}"
    export CXXFLAGS="${CXXFLAGS/-fstack-protector-strong/}"
fi

# to enable func64 interface in musl for 64-bit file system functions
export CFLAGS+=' -D_LARGEFILE64_SOURCE'
export CXXFLAGS+=' -D_LARGEFILE64_SOURCE'

# keep using xz-compressed packages, because one use of the package is to
# recover on systems with broken zstd support in libarchive
[[ $PKGEXT = .pkg.tar.zst ]] && PKGEXT=.pkg.tar.xz

prepare() {
    # pacman
    cd "${srcdir}"/pacman-${pkgver}
    local src
    for src in "${source[@]}"; do
        src="${src%%::*}"
        src="${src##*/}"
        [[ $src = pacman-*.patch ]] || continue
        msg2 "Applying pacman patch $src..."
        patch -Np1 < "../$src"
    done

    # openssl
    cd "${srcdir}"/openssl-${_sslver}
    patch -Np1 -i "${srcdir}/ca-dir.patch"
    case ${CARCH} in
        arm|armv6h|armv7h)
            # special patch to omit -latomic when installing pkgconfig files
            msg2 "Applying openssl patch openssl-3.0.7-no-atomic.patch..."
            patch -Np1 -i "${srcdir}/openssl-3.0.7-no-atomic.patch"
    esac
}

build() {
    export PKG_CONFIG_PATH="${srcdir}"/temp/usr/lib/pkgconfig
    export PATH="${srcdir}/temp/usr/bin:${PATH}"

    # openssl
    cd "${srcdir}"/openssl-${_sslver}
    case ${CARCH} in
        x86_64)
            openssltarget='linux-x86_64'
            optflags='enable-ec_nistp_64_gcc_128'
            ;;
        pentium4)
            openssltarget='linux-elf'
            optflags=''
            ;;
        i686)
            openssltarget='linux-elf'
            optflags='no-sse2'
            ;;
        i486)
            openssltarget='linux-elf'
            optflags='386 no-threads'
            ;;
        arm|armv6h|armv7h)
            openssltarget='linux-armv4'
            optflags=''
            ;;
        aarch64)
            openssltarget='linux-aarch64'
            optflags='no-afalgeng'
            ;;
    esac
    # mark stack as non-executable: http://bugs.archlinux.org/task/12434
    ./Configure --prefix="${srcdir}"/temp/usr \
                --openssldir=/etc/ssl \
                --libdir=lib \
                -static \
                no-ssl3-method \
                ${optflags} \
                "${openssltarget}" \
                "-Wa,--noexecstack ${CPPFLAGS} ${CFLAGS} ${LDFLAGS}"
    make build_libs
    make install_dev

    # xz
    cd "${srcdir}"/xz-${_xzver}
    ./configure --prefix="${srcdir}"/temp/usr \
                --disable-shared
    cd src/liblzma
    make
    make install

    # bzip2
    cd "${srcdir}"/bzip2-${_bzipver}
    sed -i "s|-O2|${CFLAGS}|g;s|CC=gcc|CC=${CC}|g" Makefile
    make libbz2.a
    install -Dvm644 bzlib.h "${srcdir}"/temp/usr/include/
    install -Dvm644 libbz2.a "${srcdir}"/temp/usr/lib/

    cd "${srcdir}"/zstd-${_zstdver}/lib
    make libzstd.a
    make PREFIX="${srcdir}"/temp/usr install-pc install-static install-includes

    # zlib
    cd "${srcdir}/"zlib-${_zlibver}
    ./configure --prefix="${srcdir}"/temp/usr \
                --static
    make libz.a
    make install

    # libarchive
    cd "${srcdir}"/libarchive-${_libarchive_ver}
    CPPFLAGS="-I${srcdir}/temp/usr/include" CFLAGS="-L${srcdir}/temp/usr/lib" \
        ./configure --prefix="${srcdir}"/temp/usr \
                    --without-xml2 \
                    --without-nettle \
                    --disable-{bsdtar,bsdcat,bsdcpio,bsdunzip} \
                    --without-expat \
                    --disable-shared
    make
    make install-{includeHEADERS,libLTLIBRARIES,pkgconfigDATA,includeHEADERS}

    # nghttp2
    cd "${srcdir}"/nghttp2-${_nghttp2_ver}
    ./configure --prefix="${srcdir}"/temp/usr \
        --disable-shared \
        --disable-examples \
        --disable-python-bindings
    make -C lib
    make -C lib install

    # c-ares
    # needed for curl, which does not use it in the repos
    # but seems to be needed for static builds
    cd "${srcdir}"/c-ares-${_cares_ver}
    ./configure --prefix="${srcdir}"/temp/usr \
        --disable-shared
    make -C src/lib
    make install-pkgconfigDATA
    make -C src/lib install
    make -C include install

    # curl
    cd "${srcdir}"/curl-${_curlver}
    # c-ares is not detected via pkg-config :(
    ./configure --prefix="${srcdir}"/temp/usr \
                --disable-shared \
                --with-ca-bundle=/etc/ssl/certs/ca-certificates.crt \
                --disable-{dict,gopher,imap,imaps,ldap,ldaps,manual,pop3,pop3s,rtsp,scp,sftp,smb,smbs,smtp,smtps,telnet,tftp} \
                --without-{brotli,libidn2,librtmp,libssh2} \
                --disable-libcurl-option \
                --with-openssl \
                --enable-ares="${srcdir}"/temp/usr
    make -C lib
    make install-pkgconfigDATA
    make -C lib install
    make -C include install

    # libgpg-error
    cd "${srcdir}"/libgpg-error-${_gpgerrorver}
    ./configure --prefix="${srcdir}"/temp/usr \
        --disable-shared
    make -C src
    make -C src install-{binSCRIPTS,libLTLIBRARIES,nodist_includeHEADERS,pkgconfigDATA}

    # libassuan
    cd "${srcdir}"/libassuan-${_libassuanver}
    ./configure --prefix="${srcdir}"/temp/usr \
        --disable-shared
    make -C src
    make -C src install-{binSCRIPTS,libLTLIBRARIES,nodist_includeHEADERS,pkgconfigDATA}

    # gpgme
    cd "${srcdir}"/gpgme-${_gpgmever}
    ./configure --prefix="${srcdir}"/temp/usr \
        --disable-fd-passing \
        --disable-shared \
        --disable-languages
    make -C src
    make -C src install-{binSCRIPTS,libLTLIBRARIES,nodist_includeHEADERS,pkgconfigDATA}

    # ew libtool
    rm "${srcdir}"/temp/usr/lib/lib*.la

    # Finally, it's a pacman!
    mkdir -p "${srcdir}"/pacman-${pkgver}/builddir
    cd "${srcdir}"/pacman-${pkgver}/builddir
    meson setup \
        --prefix=/usr \
        --includedir=lib/pacman/include \
        --libdir=lib/pacman/lib \
        --buildtype=plain \
        -Dbuildstatic=true \
        -Ddefault_library=static \
        -Ddoc=disabled \
        -Ddoxygen=disabled \
        -Dldconfig=/usr/bin/ldconfig \
        -Dscriptlet-shell=/usr/bin/bash \
        ..
    ninja
}

package() {
    cd "${srcdir}"/pacman-${pkgver}/builddir
    DESTDIR="${pkgdir}" ninja install

    rm -rf "${pkgdir}"/usr/share "${pkgdir}"/etc
    for exe in "${pkgdir}"/usr/bin/*; do
        if [[ -f ${exe} && $(head -c4 "${exe}") = $'\x7fELF' ]]; then
            mv "${exe}" "${exe}"-static
        else
            rm "${exe}"
        fi
    done

    cp -a "${srcdir}"/temp/usr/{bin,include,lib} "${pkgdir}"/usr/lib/pacman/
    sed -i "s@${srcdir}/temp/usr@/usr/lib/pacman@g" \
        "${pkgdir}"/usr/lib/pacman/lib/pkgconfig/*.pc \
        "${pkgdir}"/usr/lib/pacman/bin/*
}

