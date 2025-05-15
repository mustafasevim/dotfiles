# wpa_supplicant on Alpine Linux 

1. Install required packages
```
apk add dbus dbus-dev dbus-glib dbus-glib-dev readline-dev ncurses-dev libnl3-dev openssl-dev build-base pkgconf wget
```
2. Download wpa_supplicant source package
```
wget https://w1.fi/releases/wpa_supplicant-2.11.tar.gz
```
3. Extract wpa_supplicant2.11.tar.gz
```
tar xzvf wpa_supplicant-2.11.tar.gz
```
4. Go in to extracted wpa_supplicant2.11 folder
```
cd wpa_supplicant-2.11
```
4. Create a build configuration file that should work for standard WiFi setups by running the following command
```
cat > wpa_supplicant/.config << "EOF"
CONFIG_AP=y
CONFIG_BACKEND=file
CONFIG_BGSCAN_SIMPLE=y
CONFIG_CTRL_IFACE=y
CONFIG_CTRL_IFACE_DBUS_INTRO=y
CONFIG_CTRL_IFACE_DBUS_NEW=y
CONFIG_DEBUG_FILE=y
CONFIG_DEBUG_SYSLOG=y
CONFIG_DEBUG_SYSLOG_FACILITY=LOG_DAEMON
CONFIG_DRIVER_MACSEC_LINUX=y
CONFIG_DRIVER_NL80211=y
CONFIG_DRIVER_WEXT=y
CONFIG_DRIVER_WIRED=y
CONFIG_DPP=y
CONFIG_DPP2=y
CONFIG_EAP_FAST=y
CONFIG_EAP_GPSK=y
CONFIG_EAP_GPSK_SHA256=y
CONFIG_EAP_GTC=y
CONFIG_EAP_IKEV2=y
CONFIG_EAP_LEAP=y
CONFIG_EAP_MD5=y
CONFIG_EAP_MSCHAPV2=y
CONFIG_EAP_OTP=y
CONFIG_EAP_PAX=y
CONFIG_EAP_PEAP=y
CONFIG_EAP_PWD=y
CONFIG_EAP_SAKE=y
CONFIG_EAP_TLS=y
CONFIG_EAP_TNC=y
CONFIG_EAP_TTLS=y
CONFIG_HS20=y
CONFIG_IBSS_RSN=y
CONFIG_IEEE80211AC=y
CONFIG_IEEE80211AX=y
CONFIG_IEEE80211BE=y
CONFIG_IEEE80211R=y
CONFIG_IEEE8021X_EAPOL=y
CONFIG_INTERWORKING=y
CONFIG_IPV6=y
CONFIG_LIBNL32=y
CONFIG_MACSEC=y
CONFIG_PEERKEY=y
CONFIG_PKCS12=y
CONFIG_P2P=y
CONFIG_READLINE=y
CONFIG_SAE=y
CONFIG_SMARTCARD=y
CONFIG_TDLS=y
CONFIG_WIFI_DISPLAY=y
CONFIG_WNM=y
CONFIG_WPS=y
CONFIG_WPS_ER=y
CFLAGS += -I/usr/include/libnl3
EOF
```
5. Go in to wpa_supplicant folder
```
cd wpa_supplicant
```
6. Compile
```
make
