# ftpd-dsi

WPA2-capable FTP server for the Nintendo DSi, rebuilt against modern
libnds 2.x / calico / dswifi 2.x.

Fork of [mtheall's ftpd](https://github.com/mtheall/ftpd) via
[micsthepick's NDS port](https://github.com/micsthepick/ftpdsi).

## DSi usage

- Copy `ftpdsi.nds` to the root of the DSi SD card and launch it in DSi
  mode (e.g. via Unlaunch or TWiLight Menu++).
- WiFi connects automatically using the console's saved connections.
  In DSi mode this includes the **advanced connections 4-6, so WPA/WPA2
  networks work** (set them up in DSi System Settings > Internet >
  Advanced Setup). DS-mode connections 1-3 (open/WEP) also work.
- The server listens on port 5000; the IP is shown on screen once
  connected. Login is anonymous.

## Build

Install [devkitPro](https://devkitpro.org/wiki/Getting_Started) with the
`nds-dev` group, then:

    make nds

---

Original readme below.

# ftpd

FTP Server for 3DS/Switch/Linux.

## Features

- Appears to work well with a variety of clients.
- Supports multiple simultaneous clients. The 3DS itself only appears to support enough sockets to perform 4-5 simultaneous data transfers, so it will help if you limit your FTP client to this many parallel requests.
- Cutting-edge graphics.

## Latest Builds

CIA: https://mtheall.com/~mtheall/ftpd.cia

3DSX: https://mtheall.com/~mtheall/ftpd.3dsx

NRO: https://mtheall.com/~mtheall/ftpd.nro

CIA QR Code

![ftpd.cia](https://github.com/mtheall/ftpd/raw/master/ftpd_qr.png)

## Build and install

You must set up the [development environment](https://devkitpro.org/wiki/Getting_Started).

### 3DSX

The following pacman packages are required to build `ftpd.3dsx`:

    3dstools
    devkitARM
    libctru

They are available as part of the `3ds-dev` meta-package.

Build `ftpd.3dsx`:

    make 3dsx

### NRO

The following pacman packages are required to build `ftpd.nro`:

    devkitA64
    libnx
    switch-tools

They are available as part of the `switch-dev` meta-package.

Build `ftpd.nro`:

    make nro

## Supported Commands

- ABOR
- ALLO (no-op)
- APPE
- CDUP
- CWD
- DELE
- FEAT
- HELP
- LIST
- MDTM
- MKD
- MLSD
- MLST
- MODE (no-op)
- NLST
- NOOP
- OPTS
- PASS (no-op)
- PASV
- PORT
- PWD
- QUIT
- REST
- RETR
- RMD
- RNFR
- RNTO
- SIZE
- STAT
- STOR
- STRU (no-op)
- SYST
- TYPE (no-op)
- USER (no-op)
- XCUP
- XCWD
- XMKD
- XPWD
- XRMD

## Planned Commands

- STOU
