[Best practice] How to ship PHPUnit configuration
=================================================

PHPUnit offers quite a lot options to be set as arguments on the commandline. However this is tedious when typing over and over again.

For this reason you can create an [XML configuration file](http://www.phpunit.de/manual/current/en/appendixes.configuration.html) [phpunit.xml](http://www.phpunit.de/manual/current/en/appendixes.configuration.html) that will automatically be used by the phpunit binary.

Now you may want to include this configuration file in your projects sourcecode to be used by all participating developers and your continuous integration server. But how?

## Well, you could just commit the phpunit.xml to you repository right?

Well, yes. But then all developers who want to checkout and work on your project will have to use these settings or going through the trouble of maintaining local changes to the configuration or specifying a different one using the commandline.

## No! Use phpunit.xml.dist instead.

[Sebastian made me aware of this](http://github.com/caefer/StreamHitching/commit/e1a6cef49ea6466403e3aea533728e04139e5d80) and he is right. If you provide a phpunit.xml.dist(ribution) instead then every developer can chose whether to use your configuration or his/her own.

It is also wise to ignore the real phpunit.xml for your repository using .gitignore or svn:ignore or similar. This way everybody can use the settings he/she wants without forcing them onto others.

## How can my continuous integration server use the config?

Simple! the phpunit binary is clever enough to use any phpunit.xml.dist file if no phpunit.xml is available.

link: [http://www.testically.org/2010/08/24/best-practice-how-to-ship-phpunit-configuration/](http://www.testically.org/2010/08/24/best-practice-how-to-ship-phpunit-configuration/)

hashTags: #BestPractice #ContinuosIntegration #phpunit #SebastianBergmann
