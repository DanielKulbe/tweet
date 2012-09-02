# Tweet!
#### Put twitter on your website with tweet!, an unobtrusive javascript plugin for jquery.

## Demos & examples

See [tweet.seaofclouds.com](http://tweet.seaofclouds.com/) (original version), or the bundled `index.html` file.

## customized

See [issue #288](https://github.com/seaofclouds/tweet/issues/228) for customizion intention.

Customized at 08/31/2012 by [Daniel Kulbe](http://goo.gl/L4wtW) for [Drupal](http://drupal.org) module integration called "Tweet!"

## Source

[Download tarball](http://github.com/Umbrielsama/tweet/tarball/master)

## Features

  * small size and fast download time
  * will not slow down or pause your page while tweets are loading
  * display up to 100 tweets, as permitted by the twitter search api
  * display tweets from a twitter search, or from your own feed
  * optional verb tense matching, for human readable tweets
  * optionally display your avatar
  * optionally display tweets from multiple accounts!
  * automatic linking of @replies to users’ twitter page
  * automatic linking of URLs
  * automatic linking of #hashtags, to a twitter search of all your tags
  * converts <3 to a css styleable ♥ (we ♥ hearts)
  * customize the style with your own stylesheet or with other jquery plugins
  * customize the layout with a user-defined template function
  * supports RequireJS and other AMD-compatible javascript loaders
  * + optionally display format an absolute time

## Usage

1. Get [JQuery](http://jquery.com/). In these examples, we use [Google's AJAX Libraries API](http://code.google.com/apis/ajaxlibs/).


2. include jQuery and jquery.tweet.js files in your template's `<head>`.

        <script language="javascript" src="http://ajax.googleapis.com/ajax/libs/jquery/1.6.4/jquery.min.js" type="text/javascript"></script>
        <script language="javascript" src="/tweet/jquery.tweet.js" type="text/javascript"></script>

3. Also in `<head>`, Initialize tweet! on page load with your Username and other options

        <script type='text/javascript'>
            jQuery(function($){
                $(".tweet").tweet({
                    join_text: "auto",
                    avatar_size: 32,
                    count: 3,
                    loading_text: "loading tweets..."
                });
            });
        </script>

4. In `<body>`, include a placeholder for your tweets. They'll get loaded in via JSON. How fancy!

        <div class="tweet"></div>

5. Style with our stylesheet in `<head>`, or modify as you like!

        <link href="jquery.tweet.css" media="all" rel="stylesheet" type="text/css"/>

### Default variables

* <code>username: null</code> - [string or array] required unless using the 'query' option; one or more twitter screen names (use 'list' option for multiple names, where possible)
* <code>relative_time: true</code> - [boolean]  wether to show a relative time
* <code>format_time: "{tweet_mon}/{tweet_day}/{tweet_year} - {tweet_hour}:{tweet_minutes}"</code> - [string]   time format when display an absolute time, we use the international time format symbols
* <code>list: null</code> - [string]   optional name of list belonging to username
* <code>favorites: false</code> - [boolean]  display the user's favorites instead of his tweets
* <code>query: null</code> - [string]   optional search query (see also: http://search.twitter.com/operators)
* <code>avatar_size: null</code> - [integer]  height and width of avatar if displayed (48px max)
* <code>count: 3</code> - [integer]  how many tweets to display?
* <code>fetch: null</code> - [integer]  how many tweets to fetch via the API (set this higher than 'count' if using the 'filter' option)
* <code>page: 1</code> - [integer]  which page of results to fetch (if count != fetch, you'll get unexpected results)
* <code>retweets: true</code> - [boolean]  whether to fetch (official) retweets (not supported in all display modes)
* <code>intro_text: null</code> - [string]   do you want text BEFORE your your tweets?
* <code>outro_text: null</code> - [string]   do you want text AFTER your tweets?
* <code>join_text:  null</code> - [string]   optional text in between date and tweet, try setting to "auto"
* <code>auto_join_text_default: " I said, "</code> - [string]   auto text for non verb: "I said" bullocks
* <code>auto_join_text_ed: " I " - [string]   auto text for past tense: "I" surfed
* <code>auto_join_text_ing: " I am "</code> - [string]   auto tense for present tense: "I was" surfing
* <code>auto_join_text_reply: " I replied to "</code> - [string]   auto tense for replies: "I replied to" @someone "with"
* <code>auto_join_text_url: " I was looking at "</code> - [string]   auto tense for urls: "I was looking at" http:...
* <code>loading_text: null</code> - [string]   optional loading text, displayed while tweets load
* <code>refresh_interval: null</code> - [integer]  optional number of seconds after which to reload tweets
* <code>twitter_url: "twitter.com"</code> - [string]   custom twitter url, if any (apigee, etc.)
* <code>twitter_api_url: "api.twitter.com"</code> - [string]   custom twitter api url, if any (apigee, etc.)
* <code>twitter_search_url: "search.twitter.com"</code> - [string]   custom twitter search url, if any (apigee, etc.)
* <code>template: "{avatar}{time}{join}{text}"</code> - [string or function] template used to construct each tweet <code>li</code> - see code for available vars
* <code>filter: function(tweet) {...}</code> - [function] whether or not to include a particular tweet (be sure to also set 'fetch')

### Contribute

Bring your code slinging skills to Github and help us develop new features for tweet!

[Original Github project page](http://github.com/seaofclouds/tweet/)

    git clone git://github.com/seaofclouds/tweet.git

Report bugs at http://github.com/seaofclouds/tweet/issues

### Licensed under the MIT

[License text](http://www.opensource.org/licenses/mit-license.php)
