<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Bitcoin Address Generation – Educational Demo</title>

<!-- External crypto libraries (client-side only) -->
<script src="https://cdn.jsdelivr.net/npm/js-sha256@0.9.0/build/sha256.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/ripemd160@2.0.2/dist/ripemd160.min.js"></script>

<style>
    body {
        font-family: Arial, sans-serif;
        background: #f4f6f8;
        margin: 20px;
    }
    h1 {
        font-size: 22px;
    }
    textarea {
        width: 100%;
        height: 70px;
        font-size: 14px;
    }
    button {
        padding: 10px 18px;
        font-size: 14px;
        margin-top: 10px;
        cursor: pointer;
    }
    .box {
        background: #ffffff;
        border: 1px solid #ccc;
        padding: 10px;
        margin-top: 15px;
        word-break: break-all;
    }
    .label {
        font-weight: bold;
        margin-bottom: 5px;
    }
</style>
</head>
<body>

<h1>Bitcoin Address Generation (Conceptual)</h1>

<p>
Enter a seed phrase (12, 15, 18, 24 words or any text).  
This demo shows the cryptographic transformations step-by-step.
</p>

<textarea id="seed" placeholder="Enter seed phrase here..."></textarea>
<br>
<button onclick="generate()">Generate</button>

<div class="box">
    <div class="label">1. Seed Phrase (Input)</div>
    <div id="out-seed"></div>
</div>

<div class="box">
    <div class="label">2. SHA-256(seed)</div>
    <div id="out-sha256"></div>
</div>

<div class="box">
    <div class="label">3. RIPEMD-160(SHA-256)</div>
    <div id="out-ripemd160"></div>
</div>

<div class="box">
    <div class="label">4. Version + Hash (00 + RIPEMD-160)</div>
    <div id="out-versioned"></div>
</div>

<div class="box">
    <div class="label">5. Checksum (first 4 bytes of double SHA-256)</div>
    <div id="out-checksum"></div>
</div>

<div class="box">
    <div class="label">6. Base58Check Address (Bitcoin-like)</div>
    <div id="out-address"></div>
</div>

<script>
/* Base58 encoding (minimal implementation) */
const ALPHABET = "123456789ABCDEFGHJKLMNPQRSTUVWXYZabcdefghijkmnopqrstuvwxyz";

function base58Encode(hex) {
    let num = BigInt("0x" + hex);
    let encoded = "";

    while (num > 0n) {
        let remainder = num % 58n;
        num = num / 58n;
        encoded = ALPHABET[Number(remainder)] + encoded;
    }

    // handle leading zero bytes
    for (let i = 0; i < hex.length && hex.substr(i, 2) === "00"; i += 2) {
        encoded = "1" + encoded;
    }

    return encoded;
}

function generate() {
    const seed = document.getElementById("seed").value.trim();
    if (!seed) return;

    document.getElementById("out-seed").textContent = seed;

    // SHA-256
    const sha256Hash = sha256(seed);
    document.getElementById("out-sha256").textContent = sha256Hash;

    // RIPEMD-160
    const ripemd = new RIPEMD160();
    ripemd.update(new Uint8Array(
        sha256Hash.match(/.{2}/g).map(b => parseInt(b, 16))
    ));
    const ripemd160Hash = ripemd.digest("hex");
    document.getElementById("out-ripemd160").textContent = ripemd160Hash;

    // Version byte (00 for Bitcoin mainnet P2PKH)
    const versioned = "00" + ripemd160Hash;
    document.getElementById("out-versioned").textContent = versioned;

    // Checksum = first 4 bytes of double SHA-256
    const checksumFull = sha256(sha256(
        versioned.match(/.{2}/g).map(b => String.fromCharCode(parseInt(b, 16))).join("")
    ));
    const checksum = checksumFull.substring(0, 8);
    document.getElementById("out-checksum").textContent = checksum;

    // Base58Check
    const address = base58Encode(versioned + checksum);
    document.getElementById("out-address").textContent = address;
}
</script>

</body>
</html>
