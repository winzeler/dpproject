---
published: true
category: updates
mood: speechless
date: 2021-04-05
title: Week 13 Update - April 5
slug: Week 13 Update
layout: post
---

_I'm actually writing this on April 28th.  I got behind on the DownPaymentProject updates due to the kids' spring break (two weeks) and a home reno project to replace the flooring in the entire house.  (note: this is ongoing but it's a weekend project now)_

### Publish new main website

The website at https://downpayment.gift has finally be updated.  The old site was tweaked a little since the original version but the structure is largely the same.  

The main goal of the new site was to deokoy a template that would give us room to grow in the design and features and to launch a non-wedding focus.  The original branding was all about down payment wedding registries.  The new website is more generic to all first-time home buyers and not exclusively focused on wedding buyers.  The logo is the same, with the same green and gift wrap design.  I don't have any plans to revise the logo.  I think we would customize the colors and backgrounds on the gift logo and use it for some time to come. 

<figure class="aligncenter">
    <img width="" src="/assets/images/screenshots/oldsite-wedding.png" />
    <figcaption>Old Website, featuring the old wedding focus</figcaption>
</figure>


The new website is a more like a typical SaaS software website.  I'm on sure if that is a good thing or bad.  It's based off a Jekyll template.   I wanted to stay in the Jekyll / Bridgetown RB ecosystem.  It's using Bootstrap v4.  The old website was not using any framework.  The new site is still static, still on Netlify.

<figure class="aligncenter">
    <img width="" src="/assets/images/screenshots/newsite.png" />
    <figcaption>New site, who dis?</figcaption>
</figure>

In dropping the wedding branding, we'll hopefully drop a potential objection from partner lenders... that is... that saying "Say 'I do' to a Home Together" and "Marriage is meant for a home" is a potential Fair Lending red flag.  Our early market is still intended to be wedding registry focused, especially post-covid... but we plan to focus broadly in marketing and advertising for fair lending reasons.  FHA has long supported Bridal Down Payment Registries in guidelines and mortgagee letters... Freddie Mac specifically permits gift funds from a wedding, if the borrower's provide a marriage certificate.   The fair lending issue comes from how to market these features or guidelines.  Fair lending circa 1970's says no discrimination on 'familia status'.  End of story.  One could argue that a down payment registry is not a lending product... that is a reasonable argument.. however, we are partnering with lenders and brokers and telling them to get clients using down payment registry campaigns.  We need our marketing and positioning to be 120% in the clear.   If we were focused direct on the consumer, offering a wedding registry that supported down payment, we could market to wedding couples without worrying about fair lending advertising.   

Ultimately, we want a first time home buyer to open a down payment campaign as the first step towards homeownership.  It does not matter if they are wedding couple or not.  We expect to get the most adoption from the soon to be newlyweds, but pivoting the product to be more generic at the outset makes sense.  In future versions of the website and positioning, we'll ask if they are a wedding client and we can adjust the marketing verbiage to their situation.

_I'm searching through github and wip.co posts to remember what I did in the last month.   It seems longer than a month.  I guess it's been a looonnnngg month._

### Update Public Roadmaps

We are using [productstash.io](https://productstash.io/){:target="_blank"} for our Ideas board and Roadmaps.  It's a super clean product that is very founder friendly.  
The challenge with the roadmap, like this blog, is updating the roadmap frequently.  I've also wondered about how granular to get on the tasks or to focus on the big features only.  

<figure class="aligncenter">
    <img width="" src="/assets/images/screenshots/public-roadmap.png" />
    <figcaption>the Public Roadmap is linked from the client site and from the main site.  The target audience is clients, home-buyers</figcaption>
</figure>

[Public Roadmap](https://roadmap.downpayment.gift/home-buyers){:target="_blank"}

<figure class="aligncenter">
    <img width="" src="/assets/images/screenshots/partner-roadmap.png" />
    <figcaption>the Partner Roadmap is where most of the action is, but we link only from inside the product and help docs</figcaption>
</figure>

[Partner Roadmap](https://roadmap.downpaymentproject.com/partners){:target="_blank"}

I've updated the big stuff on the roadmap and the URL bindings.  Also the categories in the in-app Beamer widget.  Note:  I started using Beamer in-app before productstash.io.  The later support an in-app update feed... and we may consolidate to just one tool, but Beamer is nice, mature tool and it's already integrated in the code.  So there is stays.

### Bug fixes

Too many edge cases to list.  Here's a couple.

- redirect to short url after donation checkout instead of the shared_url with client name appended.  There are a few more places we need to swap to short url format but nothing I see right now.
- allow 2 letter names in the form validation.  should we allow a single letter, initial?
- replace the placeholder image because the link for this resources has an expired ssl cert and can't be relied for production.  It's a design resource.
- fix partner sub_id save issue
- feedback and bug report links for client and partner dashboard
- change "Mark as Paid" to "Mark as Received" in Client pledge history

### Update FAQ on live site

The FAQ is that pre-sales content that makes such a difference.  In the new site, we are going full on with the 0% zero fees message.  Need to make sure FAQ or other support docs does not referr to the legacy rebates approach.

<figure class="alignright">
    <img width="" src="/assets/images/screenshots/newfaq.png" />
    <figcaption>the Partner Roadmap is where most of the action is, but we link only from inside the product and help docs</figcaption>
</figure>

### First implementation of INVITATION_CODE field in client account create page

This is a greyed out field in the client account create page.  At the first version, this is a field that is not stored in the database.  We pull from configuration or from parameters on the URL and put the code string in a greyed, uneditable text box.  The text below the box refers to the INVITATION_CODE enabling the zero fees option.  In the long run, this INVITATION_CODE may be used differently.

<figure class="alignright">
    <img width="" src="/assets/images/screenshots/INVITATION_CODE.png" />
    <figcaption>the Partner Roadmap is where most of the action is, but we link only from inside the product and help docs</figcaption>
</figure>

### Lastly.. emailed Jared follow up the move forward plan

Jared has been my trusty side-kick on this project, building the original MVP using ciderr src code as a framework.  He built the first website.  Wrote the first blog post.  He's been incredibly productive on downpayment.gift from the beginning.. but as a contractor, hourly, not as an unpaid, equity co-founder.  I've been struggling on how to best allocate time or budget on development... specifically since we are fixing the current app while he has been off working on the new app.  My thinking was merging these efforts sooner, rather than later.  Unfortunately, lacking the validation from customers and partners as we are moving to launch the "old" app, it's increasing difficult to spend resources on the "new" app.  He has implemented a client side, registry page in Stimulus JS, a huge improvement on the UI that is client and donor facing.  Unfortunately, it seems like hot-swapping from the old to new and discarding the old database schema will be crazy difficult... especially at our stage.  It would be better to slowly replace bits and pieces of the system with the "new-better" instead of a wholesale move over.  In CS parlance, this is the Strangler Pattern.

After some back and forth emails, I think we came to a agreement on how to move forward.  We'll move to a REST API approach where the old codebase publishes a REST API to the new UI (or vice-versa as we get closer).  The benefit of this approach is that is should enable us to move to a native mobile client app sooner than without.  In my investor pitch deck, I refer to this as the Lemonade style app.  Client users, would be home buyers, need only download the mobile app, sign up and manage their account right from the mobile app... no web browsers or desktop centric dashboards.   This vision is a little in the future.  In fact, the lack of a mobile app is the source for some teeth grinding.  Aren't consumer apps supposed to be mobile first?  Or was that video first..?   I forget. 

I'll try to discuss this development stuff on a future podcast call.  That is, if I ever get the DownPaymentProject podcast actually going!

_Time to cut it off here.  The Week 15, 16 updates may be a little sparse due to the spring break and camping with Scouts on the weekend._
