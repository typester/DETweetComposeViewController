DETweetComposeViewController
============================

DETweetComposeViewController uses git submodules to pull in some outside code. Be sure to run 
```git submodule update --init```

## What is it?
DETweetComposeViewController is and iOS 4 compatible version of the TWTweetComposeView controller. Otherwise known as the Tweet Sheet.

## Why did we make it?
The iOS 5 TWTweetComposeViewController makes it really simple to integrate Twitter posting into you applications. However we still need to support iOS 4 in many of our applications. Having something that looks and acts like the built in Tweet Sheet allows us to have a consistent user interface across iOS versions.

## What does it look like?
![DETweetComposeViewController](https://github.com/downloads/doubleencore/DETweetComposeViewController/DETweetComposeViewController.png) ![TWTweetComposeViewController](https://github.com/downloads/doubleencore/DETweetComposeViewController/TWTweetComposeViewController.png)

As you can see they look very similar.  
  
## How do you use it?

1. Add all the files from the DETweetComposeViewController to your project.
2. Add all the files from the unofficial-twitter-sdk to your project. Thanks [lloydsparkes](https://github.com/lloydsparkes)
3. Set your Twitter OAuth Consumer Key and Secret in OAuthConsumerCredentials.h
4. Use it almost just like you would a TWTweetComposeViewController

```
#import "DETweetComposeViewController.h"
...
DETweetComposeViewController *tcvc = [[[DETweetComposeViewController alloc] init] autorelease];
[tcvc addImage:[UIImage imageNamed:@"Buzz.jpeg"]];
[tcvc addURL:[NSURL URLWithString:@"http://www.DoubleEncore.com/"]];
[tcvc addURL:[NSURL URLWithString:@"http://www.apple.com/ios/features.html#twitter"]];
[tcvc addURL:[NSURL URLWithString:@"http://www.twitter.com/"]];
[self presentModalViewController:tcvc animated:YES];
```

## What if I don't want to use the unofficial-twitter-sdk?

Just save the necessary OAuth credentils to NSUserDefaults as:

 * detwitter_oauth_token
 * detwitter_oauth_token_secret
 * detwitter_oauth_token_authorized

Then call the OAuth ```- (void) loadOAuthContextFromUserDefaults;``` method.

## What's next?

We have some TODO items in [github Issues](https://github.com/doubleencore/DETweetComposeViewController/issues). Please send us your feature requests, patches and pull requests.