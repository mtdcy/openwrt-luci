## Merge Fullcone NAT from immortalwrt

```shell
git remote add immortalwrt https://github.com/immortalwrt/luci.git
git fetch immortalwrt

# luci-base
git show f4c3b2624f
vim modules/luci-base/root/usr/share/rpcd/ucode/luci
git commit modules/luci-base/root/usr/share/rpcd/ucode/luci -m "luci-base: add system feature flag for fullcone nat"

# luci-app-firewall
git cherry-pick cbf9e16308 6da116c8ce f9b443869f

# luci-app-turboacc => defer this pick as turboacc not exists here
git cherry-pick b2099f6656 a24fa9e94c 6e83fddc58 f99c405718 88f7fcb583
```

---

# OpenWrt luci feed

[![Translation status](https://hosted.weblate.org/widgets/openwrt/-/svg-badge.svg)](https://hosted.weblate.org/engage/openwrt/?utm_source=widget)

## Description

This is the OpenWrt "luci"-feed containing LuCI - OpenWrt Configuration Interface.

## Usage

This feed is enabled by default. Your feeds.conf.default (or feeds.conf) should contain a line like:
```
src-git luci https://github.com/openwrt/luci.git
```

To install all its package definitions, run:
```
./scripts/feeds update luci
./scripts/feeds install -a -p luci
```

## API Reference

You can browse the generated API documentation directly on Github.

 - [Server side Lua APIs](http://openwrt.github.io/luci/api/index.html)
 - [Client side JavaScript APIs](http://openwrt.github.io/luci/jsapi/index.html)

## Development

Documentation for developing and extending LuCI can be found [in the Wiki](https://github.com/openwrt/luci/wiki)

## License

See [LICENSE](LICENSE) file.
 
## Package Guidelines

See [CONTRIBUTING.md](CONTRIBUTING.md) file.

## Translation status

[![Translation status](https://hosted.weblate.org/widgets/openwrt/-/multi-auto.svg)](https://hosted.weblate.org/engage/openwrt/?utm_source=widget)
