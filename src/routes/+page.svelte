<script>
  import { QRCode } from "$lib";
</script>

<svelte:head>
  <title>Test QRCode component</title>
</svelte:head>

<h1>Standard QR Code</h1>
<QRCode content="https://trasher.dk/" />

<h2>Size 50 to 200</h2>
<div>
  <QRCode size="50" content="https://trasher.dk/" />
  <QRCode size="100" content="https://trasher.dk/" />
  <QRCode size="150" content="https://trasher.dk/" />
  <QRCode size="200" content="https://trasher.dk/" />
</div>

<h2>Padding 0 to 20</h2>
<div>
  <QRCode padding="0" content="https://trasher.dk/" />
  <QRCode padding="5" content="https://trasher.dk/" />
  <QRCode padding="10" content="https://trasher.dk/" />
  <QRCode padding="20" content="https://trasher.dk/" />
</div>

<h2>Colours and background colours</h2>
<div>
  <QRCode color="#990000" content="https://trasher.dk/" />
  <QRCode color="#009900" content="https://trasher.dk/" />
  <QRCode color="#ffffff" bgcolor="#009900" content="https://trasher.dk/" />

  <QRCode color="#ffffff" bgcolor="#000000" content="https://trasher.dk/" />
</div>

<h2>Error correction L, M, Q, and H</h2>
<div>
  <QRCode errorCorrection="L" content="https://trasher.dk/" />
  <QRCode errorCorrection="M" content="https://trasher.dk/" />
  <QRCode errorCorrection="Q" content="https://trasher.dk/" />
  <QRCode errorCorrection="H" content="https://trasher.dk/" />
</div>

<h2>Responsive</h2>
<div style="height:30%;width:30%">
  <QRCode responsive="true" content="https://trasher.dk/" />
</div>

<h2>Time based one time passwords configuration sample</h2>
<div>
  <QRCode
    content="otpauth://totp/ACME%20Co:john.doe@email.com?secret=HXDMVJECJJWSRB3HWIZR4IFUGFTMXBOZ&issuer=ACME%20Co&algorithm=SHA1&digits=6&period=30"
  />
</div>
