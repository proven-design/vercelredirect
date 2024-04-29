You might be wondering, "How do I redirect my domain using Vercel if my domain is on Namecheap? Godaddy, Gandi, IONOS, Google, and ALSO account for https:// and www? 

DNS Records alone cannot allow a redirect utilizing https - so the best way I am aware of is to point to a free server that can do a permanent 301 redirect.

I recently discovered that Namecheap's redirect, the "redirect domain" section doesn't account for www. or https. I thought namecheap had a server to perform this, but the easy redirect is simply a DNS record which does not have this capability.
![image](https://github.com/proven-design/vercelredirect/assets/49770117/e8374e6d-05f0-47ec-a060-9fa3e7c5a7b9)

## This repo is the minimum required in order to implement a redirect, all you have to do is point your domain's DNS to Vercel.

## Step 1
- Copy this repository or at the very least the vercel.json
- Update the URL you want it to redirect to in vercel.json `"destination": "https://myURLgoeshere.com"`

## Step 2
- Set up a new project on Vercel
- Select your github and point to your repository
- Just hit deploy, nothing else is necessary when configuring

## Step 3 - Add 
- Add a domain to your vercel project
- Click on Nameservers and select "add to vercel DNS" (language here might be a little different)
- It should list the Nameservers to point your domain to, it might look something like this 
`ns1.vercel-dns.com` 
`ns2.vercel-dns.com`

## Final Step - Change domain nameservers
- Change your domain's nameservers to the vercel nameservers
On Namecheap it looks like this
![image](https://github.com/proven-design/vercelredirect/assets/49770117/ff2dc6fd-eb6d-414e-8a6b-3c328763d043)
- When the DNS successfully propagates (when it updates), on Vercel it should look something like below:
![image](https://github.com/proven-design/vercelredirect/assets/49770117/6bfe45da-ea82-4168-96c4-fd3158a409e3)
(Note this could take up to a day, I've never seen it take more than 5 minutes, but it's usually less than 1 minute.)
