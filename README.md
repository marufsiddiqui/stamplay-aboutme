stamplay-aboutme
===================

**This project is built on the [Stamplay](https://stamplay.com) platform and [BackboneJS](http://backbonejs.org) to show how to build your own [About.me](http://about.me) in super short time.**

You can test it anytime simply creating a new project on Stamplay and uploading all the frontend assets with our client or our browser based code editor. 

Feel free to implement more cool features (see the last paragraph for ideas), contribute to this repo or clone it to use it by your own scopes. For any question drop an email to [giuliano.iacobelli@stamplay.com](mailto:giuliano.iacobelli@stamplay.com)

-----------------------
## About.me clone

This is a demo of what you can achieve with [Stamplay](http://stamplay.com).

It's somewhat a clone of [About.me](http://about.me). [View demo](https://68a5fe.stamplay.com/)

Currently, in order to show how to leverage Stamplay APIs and keep it simple we used [BackboneJS](http://backbonejs.org) to implement the client side logic. The clone with let our users to:

* Login with Facebook
* Configure the personal page
* Compliment pages of other users
* Let visitors of connect with the owner of the about.me page via email

Best of all, we used BackboneJS and Grunt to compile the assets to be compliant to the actual Stamplay apps' skeleton. Prepare to be amazed.

-----------------------
# Anatomy

HNclone is built around the following apis (components) of Stamplay

* [Users](http://docs.stamplay.apiary.io/#user)
* [Form](http://docs.stamplay.apiary.io/#form)
* [Custom Objects](http://docs.stamplay.apiary.io/#customobject)
* [Email](http://docs.stamplay.apiary.io/#email)
* **Facebook Post**

## Requirements

Go to [your account](http://editor.stamplay.com/apps) and create a new app.

Other required services :

* A [Facebook App](http://developers.facebook.com/apps) to setup Facebook Login auth


## Configuring the components

After creating a new app on [Stamplay](https://editor.stamplay.com) let's start by picking the component we want to use in our app that are: **User**, **Email**, **Custom Objects** and **Form**.

Lets see one-by-one how they are configured:

### User
the app leverages Facebook Login to provide an easy login to its users. In order to activate yours you need to get an APPID and APPSecret on [Facebook Developer's portal](http://developers.facebook.com/apps), create an app and add Stamplay.com as authorized domain as you can see in the pic below. 

![Facebook app settings](http://blog.stamplay.com/wp-content/uploads/2014/07/Schermata-2014-07-22-alle-17.43.24.png "Facebook app settings")

now you have the data to configure Facebook Login on your app's user module. Go back on Stamplay, select the user component, add Facebook as signup service and then cut and paste the App ID and App Secret and click save.

### Custom Object
For our About.me clone we use this module to represent the **AboutPage** that users can create and then share. The **AboutPage** object will contain all the informations so here we need to model those as attributes:

* Name: `bg`, Type: `file`, The background image of the page
* Name: `biopic`, Type: `file`, The avatar image of the page
* Name: `name`, Type: `string`, The title of the page
* Name: `headline`, Type: `string`, User's favorite quote
* Name: `biography`, Type: `string`, Text describing user's bio
* Name: `locations`, Type: `array_string`, A list of user's locations
* Name: `bg_color1`, Type: `string`, The first RGB color for the layout
* Name: `bg_color2`, Type: `string`, The second RGB color for the layout
* Name: `header_color`, Type: `string`, The header RGB color for the layout
* Name: `interests`, Type: `array_string`, A list of user's interests
* Name: `hobbies`, Type: `array_string`, A list of user's hobbies
* Name: `educations`, Type: `array_string`, A list of user's educatin activities
* Name: `user`, Type: `user relation`, The reference to the owner of this page
* Name: `birthplace`, Type: `string`, The birthplace
* Name: `email`, Type: `string`, The email on which our user can be reached out 

After setting up this Stamplay will instantly expose Restful APIs for our newly created AboutPage resource on the following endpoint `https://APPID.stamplay.com/api/cobject/v0/aboutpage`

### Form 

Form component is used to create a contact form in the AboutPage of our users so that visitors will be able to write to the owner of the page without knowing the email address. The form will hav 4 fields:

* Name: `email`, Type: `text`, The sender's email address
* Name: `name`, Type: `text`, The sender's email name
* Name: `message`, Type: `text`, The message
* Name: `to`, Type: `text`, User's favorite quote




# todo be finished


-----------------------
# Cloning

First, clone this repository :

    git clone git@github.com:Stamplay/stamplay-aboutme.git
    
Or download it as a zip file
	
	https://github.com/Stamplay/stamplay-aboutme/archive/master.zip 

Then you need to upload the frontend files in your app and you can do it in two ways:

* Copy/Upload them via the Layout section of your app on Stamplay editor
* [Get](http://cdn.stamplay.com/stamplay-sync/stamplay-sync.zip) and run **Stamplay Sync**, make it download the frontend assets of your app and then replace them with the ones you got from this repo. Stamplay Sync will upload everything for you on your app.


-----------------------
# Next steps

Here are a few ideas for further improvement :

* Add the "users who complimented you" as About.me does
* _Your idea here… ?_

Again, for any questions drop an email to [giuliano.iacobelli@stamplay.com](mailto:giuliano.iacobelli@stamplay.com) :)

Ciao!
