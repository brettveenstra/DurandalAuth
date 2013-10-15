## What´s this?

This template is a port of the default ASP MVC 4 Internet template and its security system.

The included features are:

- Forms and oAuth authentication and authorization using SimpleMembership providers

- Authorization in Durandal views

- AntiForgery tokens

- Model validation both client (knockout validation) and server (data attributes)

- UnitOfWork and Repository patterns both client and server

- Using Breeze JS in the client for better data management

- pushState enabled

- Styled with Bootstrap 3


##Check it out!! ...

... the [sample site](https://durandalauth.azurewebsites.net) and play with it

##Weyland config

When you make changes over this project you are going to need to optimize the Durandal files, so remember, you have to install **node** and **weyland**

```
//install node and run this in your command line
npm install -g weyland
weyland build
```

Or you can follow this links:

[Building with weyland](http://durandaljs.com/documentation/Building-with-Weyland/)

[Automating builds with Visual Studio](http://durandaljs.com/documentation/Automating-Builds-with-Visual-Studio/)


##About pushState

Since Durandal 2.0 we can use pushState so this feature is enabled by default. If you prefer hashes you can always set pushState to false in shell.js

```
.activate({ pushState : true }); // set to false for using hash style url´s

```

##About SEO Optimization

The template is ready to be SEO crawlable. DurandalAuth implements the [google ajax crawling scheme](https://developers.google.com/webmasters/ajax-crawling/docs/getting-started) for pages without hash fragments. You need the default pushstate option enabled.

I created a interface (Helpers/ISnapshot.cs) that needs to be implemented in order to work.

The default implementation uses [a new project I created called AzureCrawler](https://github.com/yagopv/azurecrawler)

This new project is a Worker Role ready to be deployed to Windows Azure and serving a REST Web API via OWIN. The Web API executes a phantomjs process when receiving requests and returns html snapshots. Moreover, AzureCrawler can save the snapshot to Azure Storage and keep it there with the expiration date you choose, so next time the page is requested for any bot, the stored snapshot will be served.

I created AzureCrawler like a separate project but it´s easy to bring all the concepts from AzureCrawler to your own project if you want to keep it in the same solution. Another option is creating your own implementation of ISnapshot.cs.

Check durandalauth site at google:

```
site:durandalauth.azurewebsites.net
```
