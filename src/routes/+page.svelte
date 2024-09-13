<script>
  import { QRCode } from "$lib";

  const content = "https://www.npmjs.com/package/@trasherdk/svelte-qrcode";
  const imageUrl = "/fumlersoft-shield-64.png";
</script>

<svelte:head>
  <title>Test QRCode component</title>
</svelte:head>

<h1>Standard QR Code</h1>
<div class="centered">
  <QRCode {content} />
</div>

<h2>Size 50 to 200</h2>
<div class="centered">
  <QRCode size="50" {content} />
  <QRCode size="100" {content} />
  <QRCode size="150" {content} />
  <QRCode size="200" {content} />
</div>

<h2>Padding 0 to 20</h2>
<div class="centered">
  <QRCode padding="0" {content} />
  <QRCode padding="5" {content} />
  <QRCode padding="10" {content} />
  <QRCode padding="20" {content} />
</div>

<h2>Colours and background colours</h2>
<div class="centered">
  <QRCode color="#990000" {content} />
  <QRCode color="#009900" {content} />
  <QRCode color="#ffffff" bgcolor="#009900" {content} />
  <QRCode color="#ffffff" bgcolor="#000000" {content} />
</div>

<h2>Error correction L, M, Q, and H</h2>
<div class="centered">
  <QRCode errorCorrection="L" {content} />
  <QRCode errorCorrection="M" {content} />
  <QRCode errorCorrection="Q" {content} />
  <QRCode errorCorrection="H" {content} />
</div>

<h2>Responsive</h2>
<div class="centered">
  <div class="resize">
    <QRCode responsive="true" {content} />
  </div>
</div>

<h2>Time based one time passwords configuration sample</h2>
<div class="centered">
  <QRCode
    size="300"
    content="otpauth://totp/ACME%20Co:john.doe@email.com?secret=HXDMVJECJJWSRB3HWIZR4IFUGFTMXBOZ&issuer=ACME%20Co&algorithm=SHA1&digits=6&period=30"
  />
</div>

<style>
  .centered {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 1rem;
    flex-wrap: wrap;
  }
  h1,
  h2 {
    text-align: center;
    width: 100%;
  }
  .resize {
    height: 20%;
    width: 20%;
    resize: horizontal;
    overflow: auto;
  }
</style>
