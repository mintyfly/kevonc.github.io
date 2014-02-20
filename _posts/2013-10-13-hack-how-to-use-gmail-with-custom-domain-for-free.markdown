---
layout: post
title: "Hack: How to Use Gmail with Custom Domain for Free"
date: 2013-10-13 11:46
categories: hack
tags: [gmail, custom domain, free email]
---

When I checked Google Apps for Business last week, I found out that to set up your custom domain to use Gmail, you would have to pay 5 USD per month per user. It was no longer free! A year ago, I was using it for my startup and I remembered it could host up to 10 users for free. To figure out a way so that I can continue using Gmail for my own domain for free, I set out to hack it. And this is how I do it.

<h4>Step 1</h4>
Of course, to start off, you will need to register your own domain name. I use <a href="http://www.namecheap.com/?aff=57162">Namecheap</a> because it is easy and it covers a lot of extensions, including my new favorite .us (which is only 3 USD per year).

<h4>Step 2</h4>
After getting your domain, let's say yourcustomdomain.com here. You have to login into your Namecheap account and set the DNS to point to your own hosting server. I use <a href="http://secure.hostgator.com/~affiliat/cgi-bin/affiliates/clickthru.cgi?id=bunkev">Hostgator</a> for years already because of its great customer service. I usually go on to their online chat and get my question answered within 5 minutes.

<h4>Step 3</h4>
Now, you need to register a new Gmail account to connect with your email from custom domain. This will be the account you access everyday. I created kevonishappy@gmail.com.

<h4>Step 4</h4>
Head back to Hostgator, log in to the control panel. Create new email account kevon@yourcustomdomain.com and set up email forwarder so that kevon@yourcustomdomain.com will forward all of its email to kevonishappy@gmail.com.

<img src="http://i.imgur.com/U6bA7KA.jpg" title="Hosted by imgur.com"/>

<h4>Step 5</h4>
Really this is the last step, log into your Gmail account kevonishappy@gmail.com, and do <strong>Settings</strong> -> <strong>Accounts</strong>. Under <strong>Send mail as:</strong>, click <strong>Add another email address you own</strong>. A pop up window should come up and ask for more information, now enter your name (Kevon) and email address (kevon@yourcustomdomain.com). Leave the <strong>Treat as an alias</strong> checked.

Next step you would want to choose <strong>Send through yourcustomdomain.com SMTP servers</strong>. For SMTP Server: enter mail.yourcustomdomain.com. For Username and Password, enter your credentials for your kevon@yourcustomdomain.com. After that, simply go to your webmail, which is yourcustomdomain.com/webmail, and log in to verify the connection.

<img src="http://i.imgur.com/81mxtCk.jpg" title="Hosted by imgur.com"/>

<h4>Final Words</h4>
Now not only you receive all your emails from kevon@yourcustomdomain.com in your kevonishappy@gmail.com account, you can also send or reply email as kevon@yourcustomdomain.com! How amazing and cost-effective is that for a startup company? I hope this helps out anyone who has this trouble.