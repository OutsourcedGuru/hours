# Hours
A PhoneGap client-side app for connecting to a REST-ish ASPX SQL server-side.

### PhoneGap

I'm using PhoneGap as the cross-platform framework since I need support for both iOS and Android smartphones.  This is a work-related project in which I'm adding mobile support to a web-based app that I've already written.

### Server-side code

The server side doesn't have to be Microsoft ASPX pages but I'm grafting this onto an existing project and that's what the existing pages are so it's convenient enough.  It's co-located on a SQL Server in IIS; each ASPX page includes a directive to be ASP-compatible, for what it's worth.  The server side code currently isn't included in this repository but responds via the following using an ASP-friendly tweak to REST interface:

### Table READs

*http://servername/reports/hours/mobile*/**customers**
*http://servername/reports/hours/mobile*/**jobs**
*http://servername/reports/hours/mobile*/**users**
*http://servername/reports/hours/mobile*/**time**

The **servername** and **/reports/hours/mobile/** folder location is from my own project but can be easily customized in one place in your project's **js/config.js**.

Each smartphone's UUID uniquely identifies the user lookup so that they don't have to authenticate.  This comes in via a **/?uuid=value** argument pair for every call.  I'm currently hard-coding those UUIDs server-side since I don't feel like creating another table in SQL Server (yet).

### User records

There are two user types:  admins and users.  An admin would be able to add customer, user and job records.  A user would be able to add only time records for himself/herself.  Since there's only one admin--myself--I've hard-coded this in the server-side code for simplicity.

### SQL to JSON

I'm converting the SQL records into JSON during server-side reporting to make this easier for PhoneGap/jQuery to process the records.

### jQuery Mobile

I'm taking advantage of jQuery Mobile for a consistent rendering of buttons and to easily manipulate the DOM.

|Donate||Cryptocurrency|
|:-----:|---|:--------:|
| ![eth-receive](https://user-images.githubusercontent.com/15971213/40564950-932d4d10-601f-11e8-90f0-459f8b32f01c.png) || ![btc-receive](https://user-images.githubusercontent.com/15971213/40564971-a2826002-601f-11e8-8d5e-eeb35ab53300.png) |
|Ethereum||Bitcoin|
