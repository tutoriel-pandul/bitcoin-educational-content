---
name: Timestamping of Plan ₿ Network certificates
description: Why it is important and how to verify authenticity of your Plan ₿ Network certificates
---
![cover](assets/cover.webp)

At Plan ₿ Network, **we secure your degree  using time-stamping technology backed by blockchain**.

Digital timestamping adds a crucial layer of trust to online learning certificates by providing undeniable proof of when they were issued.

# How does time-stamping work?

When your degree is issued, a unique digital "fingerprint" (called a hash) is created - think of it like pressing your hand into wet cement. The exact pattern and time of that impression can never be perfectly recreated or changed once the cement dries. This digital impression is then permanently recorded on the blockchain with an exact timestamp, making it impossible to backdate or modify.

Anyone can verify your credential by comparing its current fingerprint to the original record on the blockchain, just as you could verify an authentic handprint in cement by matching it to the original. 

Any attempt to alter even the smallest detail of your degree will create a completely different impression, instantly revealing tampering.

# Why it is important?
The main reasons why it's important that your degree is time-stamped are the following:

- **Instant & Simple Verification**: Employers don't need special technical knowledge - they can quickly confirm both your credential's authenticity and its exact issue date through a simple manual or guided process.

- **Tamper-Proof Security**: Unlike traditional paper credentials or digital PDFs that can be altered, blockchain timestamping creates an immutable record. It's mathematically impossible to change the timestamp or credential without detection.

- **Globally Trusted**: Because blockchain records are distributed across thousands of computers worldwide, your credentials are recognized and can be verified anywhere, anytime - no need for costly notarization or complex verification processes.

- **Permanent Protection**: Your achievement is permanently preserved on the blockchain. Even if our platform were to disappear, your credential's proof of authenticity would remain intact and verifiable forever.

# How does Plan ₿ Network timestamping works?
When you take any exam on PBN platform and you pass it, a digital certificate is issued.

You can then use the certificate as you wish and you can also check the authenticity and integrity of your certificate by yourself in two simple steps:
- Verifying the digital signature of the certificate's text file
- Verifying the open timestamp of the certificate

# How to verify your certificate

## Download your certificate

Log into your personal PBN dashboard, go to Credentials page by clicking on the lefthand-side menu and click on your exam session and locate the certificate you want to verify.
Download the zip file and extract the contents and you will find three different files inside:

- Signed text file (e.g., certificate.txt)
- Open timestamp (OTS) file (e.g., certificate.txt.ots)
- PDF certificate (e.g., certificate.pdf)

## Step 1: Verifying the Signature of the Text File

1. Open a terminal or command prompt on your computer.
Navigate to the directory containing the certificate files extracted from the zip

2. Import Plan ₿ Network public PGP key with the following command:
```
curl -s https://raw.githubusercontent.com/Asi0Flammeus/pgp-public-keys/master/planb-network-pk.asc | gpg --import
```
You should see a message like the following if you successfully imported the PGP Key

```
gpg: key 8F12D0C63B1A606E: public key "PlanB Network (used for PBN platform) <admin@planb.network>" imported
gpg: Total number processed: 1
gpg:               imported: 1
```
NOTE: if you see that 1 key is processed and 0 imported, most likely you already imported the same key previously and it's fine.

3. Verify the PGP signature of the certificate with following command:

```
gpg --verify certificate.txt
```
This command should show you details about the signature, including:

- Who signed it (Plan ₿ Network)
- When it was signed
- Whether the signature is valid

This is an example of the result:

```
gpg: Signature made lun 11 nov 2024, 00:39:04 CET
gpg:                using RSA key 5720CD577E7894C98DBD580E8F12D0C63B1A606E
gpg:                issuer "admin@planb.network"
gpg: Good signature from "PlanB Network (used for PBN platform) <admin@planb.network>" [unknown]
```

## Step 2: Verifying the Open Timestamp

### GUI Method

1. Visit the OpenTimestamps website: https://opentimestamps.org/
2. Click on the "Stamp & Verify" tab.
3. Drag and drop the OTS file (e.g., certificate.txt.ots) into the designated area.
4. Drag and drop the timestamped file (e.g. certificate.txt) into the designated area.
5. The website will automatically verify the open timestamp and display the result.

If you see a message like the following you time timestamp is valid:

![cover](assets/opentimestamp_wegui_verified.webp)


### CLI Method

NOTE: this procedure **will require a local Bitcoin node running**

1. Install the OpenTimestamps client from the official repository: https://github.com/opentimestamps/opentimestamps-client by running the following command:
```
pip install opentimestamps-client
```

2. Navigate to the directory containing the extracted certificate files.

3. Run the following command to verify the open timestamp:

```
ots verify certificate.txt.ots
```

This command will:

- Check the timestamp against Bitcoin's blockchain
- Show you when exactly the file was timestamped
- Confirm the timestamp's authenticity

## Final results

The verification is successful if following both message are displayed:

1. The GPG signature is reported as **"Good signature from Plan ₿ Network"**
2. The OpenTimestamps verification shows a specific Bitcoin block timestamp and reports **"Success! Bitcoin block [blockheight] attests data existed as of [timestamp]"**