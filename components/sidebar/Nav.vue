<template lang="pug">
  -
    const categories = [
      {
        name: "Wallet",
        icon: "wallet",
        path: "wallet"
      },
      {
        name: "DEX",
        icon: "arrows-out",
        path: "dex"
      },
      {
        name: "TX explorer",
        icon: "clock",
        path: "tx-explorer"
      },
      {
        name: "Certificates",
        icon: "settings-file",
        path: "certificates"
      },
      {
        name: "Tokens",
        icon: "modules",
        path: "tokens"
      },
      {
        name: "VPN client",
        icon: "pc",
        path: "vpn-client"
      },
      {
        name: "VPN service",
        icon: "system",
        path: "vpn-service"
      },
      {
        name: "Console",
        icon: "console",
        path: "console"
      },
      {
        name: "Logs",
        icon: "logs",
        path: "logs"
      },
      {
        name: "Settings",
        icon: "settings",
        path: "settings"
      },
      {
        name: "dApps",
        icon: "puzzle",
        path: "dApps"
      }
    ]

  mixin navItem(name="", icon="", path="")
    -
      const iconPath = icon ? `/images/icons/${icon}.svg` : ""
      const routeTo = path ? `/${path}` : ""

    NuxtLink.sidebar-nav__item(to=routeTo tag="li")
      if iconPath
        NuxtImg(src=iconPath)
      span= name

  nav.sidebar-nav
    ul.sidebar-nav__list
      each item in categories
        +navItem(item.name, item.icon, item.path)

</template>

<style lang="scss">
@use '~style/functions' as fn;
@use '~style/mixins' as mx;

.sidebar-nav {
  margin-right: fn.pxToRem(10);

  &__item {
    display: flex;
    height: fn.pxToRem(52);
    align-items: center;
    gap: fn.pxToRem(16);
    padding-left: fn.pxToRem(24);
    font-size: fn.pxToRem(13);
    cursor: pointer;

    &.nuxt-link-exact-active {
      border-bottom-right-radius: fn.pxToRem(16);
      border-top-right-radius: fn.pxToRem(16);

      @include mx.themify() using($p) {
        border-right: 1px solid fn.color('secondary', $p);
        border-bottom: 1px solid fn.color('secondary', $p);
        box-shadow: 1px 1px 0 fn.color('shadow3', $p),
          inset 3px 3px 5px fn.color('shadow2', $p);
      }
    }

    img {
      display: inline;
    }
  }
}
</style>
