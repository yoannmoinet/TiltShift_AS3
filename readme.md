This is a simple class for doing some tiltshift on any picture.
Just instantiate a new Tiltshift object with your arguments.

#### Example ####

You can load any asset from your library

	var image:Asset_image = new Asset_image(535, 302);
	var myImage:Tiltshift = new Tiltshift(0.5,0.5,5,-40,"asset",image);

or with an url

	var myImage2:Tiltshift = new Tiltshift(0.5,0.5,5,-40,"url",'./assets/image.jpg');


#### Constructor ####


	new Tiltshift(size of focal,position of focal on the image, blur value, angle, image type(url or asset), asset or url);

#### Fla file ####

For those who can't open the fla file because of CS5.
Here is the code inside :

	import com.Tiltshift;
	import flash.display.MovieClip;
	import flash.events.Event;

	var mc_content:MovieClip = new MovieClip();
	var mc_content2:MovieClip = new MovieClip();

	//load new asset from library
	var image:Asset_image = new Asset_image(535, 302);

	//new Tiltshift(size,position, blur, angle, image type, image/url);
	var myImage:Tiltshift = new Tiltshift(0.5,0.5,5,-40,"asset",image);

	//or with an url
	var myImage2:Tiltshift = new Tiltshift(0.5,0.5,5,-40,"url",'./assets/image.jpg');
	//it dispatches an event "LOADED" once it's loaded.
	myImage2.addEventListener("LOADED", f_init);


	function f_init(evt:Event):void
	{
		mc_content.y = 35;
		mc_content.addChild(myImage);
		mc_content2.addChild(myImage2);
		mc_content2.y = stage.stageHeight - mc_content2.height;
		addChild(mc_content);
		addChild(mc_content2);
		trace(myImage2.height);
	}

After pasting it on the first frame, importing an image in the library and export for actionscript with class name 'Asset_image'.
Tweaking stage size etcÉ run it.
You may also add folders 'com' and 'assets' to your root.

#### Enjoy ! ####

