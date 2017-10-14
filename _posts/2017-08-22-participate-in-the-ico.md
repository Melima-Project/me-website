---
layout:     post
title:      How-to participate in the ICO
date:       2017-08-22
categories: [ICO]
lang: en 
permalink: /ico-participate/
---

## Do your howework

- Check [contract source](https://github.com/Melima-Project/me-smart-contract)
- Read [Main Rules]({{ site.baseurl }}/#ico), and ICO details
- Check [me-core](https://github.com/Melima-Project/me-core) and [me-web](https://github.com/Melima-Project/me-web) repositories
- Test Melima in current state with [Getting started]({{ site.baseurl }}/getting-started/) guide
- Check [whitepaper]({{ site.baseurl }}/whitepaper.pdf) (could be added later)
- Ask us a question in [Twitter](https://www.reddit.com/r/melima/), [Reddit](https://www.reddit.com/r/melima/) or on [Steemit](https://steemit.com/@melima)

## Pre instrustions

You need to select your role in this ICO. You could just support us, or became a stackholder.

**Supporter**

- Can contribute only small UBQ amount ( < 100 UBQ)
- Don't want to share valid email

**Stackholder**

- Can contribute 100 or more UBQ
- Can share valid email (inlude in data field)
- Applicable for [stackholder share]({{ site.baseurl }}/ico-faq/#stackholdershare)

  > *Check [Creating value for ME Token](https://melima.me/me-value/)* 

We specially created ME Token ICO in a way to make both small investors and serious investors benefit:

- ICO runs on top [UBQ](https://ubiqsmart.com/) and this means afordable price and fair distribution
- UBQ platform has nice grow potenticial and same apply to any token on top UBQ platform
- 30 ME bonus for every investment less or equal one stack
- 20 ME bonus in first 5 days

  > *Minimum amount to invest is 0.1 UBQ*  
  > *Yes, this means that you can invest in 10 ME and receive extra 50 ME or 30 ME as supporter*


## Short instructions

After you got (see [How-to buy UBQ]({{ site.baseurl }}/buy-ubq/)) UBQ, you can participate in the ICO.  
First you need to wait for ***ICO Start Date Announcement*** (End of November - December 2017).  
And when ICO starts, you need to [accept our main rules]({{ site.baseurl }}/#ico).  
After you accepted rules, you should follow instructions and verify contract address.  
And in case contract address you see on the webpage is correct, you can send funds (from your own wallet) to the contract address.
    
## Pyrus detailed instructions

Pyrus is myetherwallet fork for UBQ, and recommended wallet, if you don't wait for full blockchain download.

Instructions identical for [online](https://pyrus.ubiqsmart.com/) Pyrus version, Pyrus as [Chrome extension](https://chrome.google.com/webstore/detail/pyrus-cx/kkllochpehlephblgmhibpmgmeagkbfa) and for [offline](https://github.com/ubiq/pyruswallet/releases) Pyrus.

### Offline wallet

You can [download](https://github.com/ubiq/pyruswallet/releases) Pyrus, for offline use.

### Instructions

In case you didn't have a wallet, you need generate new wallet first. Also, don't forget to save and backup your keystore file.
After you created your wallet, you need to open your wallet. Select ***Send UBQ & Tokens***, choose your keystore file (usually `.json` file) and type your password.  
Now, you ready to send your funds to ME Token Contract address, and also if you want to apply for [stackholder status]({{ site.baseurl }}/ico-faq/) you need to add your valid email to the data field in hex (without spaces).  
You can use JavaScript converter from this page to convert your email to hex without spaces (and newlines). Or you can use this command in your shell:

```bash
echo -n "example@example.org" | od -A n -t x1 | tr -d '\r\n' | sed "s/ //g"
```

    
{% include tools/emailhex.html %}

![Send Transaction](/img/post-images/send_transaction.png)

After you generated transaction you also need to review it and send.


## Fusion detailed instructions

First you need to [download](https://github.com/ubiq/fusion/releases) Fusion.  
In case you didn’t have a wallet, you need generate new wallet (create new account) first. Also, don’t forget to save and backup your keystore file.  
Blockchain synchronization could take some resonable time, depending from you connection and location.  
After you need to select ***Send*** tab and click ***Show more options*** to show data field.  
Now, you ready to send your funds to ME Token Contract address, and also if you want to apply for [stackholder status]({{ site.baseurl }}/ico-faq/) you need to add your valid email to the data field in hex (without spaces).   
You can use JavaScript converter from this page (you can find it in Pyrus section).



