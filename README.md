# QR Code generator for Svelte

## Note

This is a fork of https://github.com/bonosoft/sveltekit-qrcode

The original package is not maintained and does not support Svelte 5.

## Install
Use your package manager to install the module directly from GitHub:

```shell
npm install @trasherdk/svelte-qrcode
```

## Adding QR Codes to a svelte file in SvelteKit
Now you can start adding QR Codes to your pages.
```ts
<script lang="ts">
	import QRCode from "@trasherdk/svelte-qrcode"
</script>

<QRCode content="Test"></QRCode>
```

![Alt text](https://github.com/trasherdk/svelte-qrcode/raw/main/readme/sample1.svg)

# Quick Response Codes
While conventional bar codes are capable of storing a maximum of approximately 20 digits, QR Code is capable of handling several dozen to several hundred times more information.

QR Code is capable of handling all types of data, such as numeric and alphabetic characters, Kanji, Kana, Hiragana, symbols, binary, and control codes. Up to 7,089 characters can be encoded in one symbol.

# Content
Content is the text that needs to be send to the code reader. The text is normally an URL to a web site, or a code that is used by an application, for example in handling secrets in time based one time password applications.

```ts
<QRCode content="https://trasher.dk/"/>
```

# Size, padding and responsive
You can set the size used for generation, the larger the size, the more information you are able to store in the QR code. The size is also used for the container in pixels. You can also specify the padding in module units, and recommended minimum is 4.

With the repsponsive settings enabled, the size settings will only be used in the code calculation, and the container will addapt and use all available space in it's parent element.

```ts
<QRCode size="50" content="https://trasher.dk/"/>

<QRCode padding="10" content="https://trasher.dk/"/>

<QRCode responsive='true' content="https://trasher.dk/"/>
```

# Colours
With the colour settings, you can control both the front and background colour.

```ts
<QRCode color="#009900" content="https://trasher.dk/"/>

<QRCode color="#ffffff" bgcolor="#009900" content="https://trasher.dk/"/>
```

![QR Code Color Examples](https://github.com/trasherdk/svelte-qrcode/raw/main/readme/sample2.svg)

## QR Code error correction
QR Code has error correction capability to restore data if the code is dirty or damaged. Four error correction levels are available for users to choose according to the operating environment. Raising this level improves error correction capability but also increases the amount of data QR Code size.
To select error correction level, various factors such as the operating environment and QR Code size need to be considered. Level Q or H may be selected for factory environment where QR Code get dirty, whereas Level L may be selected for clean environment with the large amount of data. Typically, Level M (15%) is most frequently selected.

* Level L  Approx 7%
* Level M  Approx 15%
* Level Q  Approx 25%
* Level H  Approx 30%

```ts
<QRCode errorCorrection='L' content="https://trasher.dk/"/>

<QRCode errorCorrection='M' content="https://trasher.dk/"/>

<QRCode errorCorrection='Q' content="https://trasher.dk/"/>

<QRCode errorCorrection='H' content="https://trasher.dk/"/>
```

# For use with Time based one time passwords (TOTP)
Sample URL for a John Doe user on the Acme app:
```ts
<QRCode content="otpauth://totp/ACME%20Co:john.doe@email.com?secret=HXDMVJECJJWSRB3HWIZR4IFUGFTMXBOZ&issuer=ACME%20Co&algorithm=SHA1&digits=6&period=30"/>
```

![QR Code TOTP Example](https://github.com/trasherdk/svelte-qrcode/raw/main/readme/sample3.svg)
