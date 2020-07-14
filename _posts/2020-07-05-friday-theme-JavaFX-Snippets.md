---
title: JavaFX Snippets
tags:
 - code
 - syntax highlighting
---

I am currently doing some projects on JavaFX. Here in this blog, I've tried to gather some short queries I've had while doing these projects. These codes have been collected from the Internet and work perfectly. So to speak, these are mere code snippets, not a whole working code or package.



<h3 style = "color: purple;">1. Converting java.awt BufferedImage to javafx.scene.image.Image</h3>
Here, we pass the BufferedImage `bufferedImage` as a parameter to the toFXImage method of SwingFXUtils class. It returns an `javafx.scene.image.Image` type object. If you use IntellIJ, then automatic import suggestions will appear.

{% highlight liquid%}
{% raw %}
{% highlight javascript %}
Image image = SwingFXUtils.toFXImage(bufferedImage, null);
{% endhighlight %}
{% endraw %}
{%endhighlight%}

<h3 style = "color: purple;">2. Converting WritableImage to javafx.scene.image.Image</h3>
We can save a WritableImage `writableImage` as an image file with `ImageIO.write()` method. The path of the file (`filePath`) just has to be mentioned. We can also pass an OutputStream as the third parameter.

{% highlight liquid%}
{% raw %}
{% highlight javascript %}
ImageIO.write(SwingFXUtils.fromFXImage(writableImage, null), "png", new File(filePath));
{% endhighlight %}
{% endraw %}
{%endhighlight%}

<h3 style = "color: purple;">3. Working with javafx.robot.Robot</h3>
In order to use this class, one should have JavaFX - 11 or higher. I prefer to use the higher ones. Besides, the robot object can work only in the main event thread. One cannot use this in other threads, because it will throw Exception. Below, is a declaration of Robot object.
{% highlight liquid%}
{% raw %}
{% highlight javascript %}
Robot robot = new Robot();
{% endhighlight %}
{% endraw %}
{%endhighlight%}
More info about [Robot][robot] class.

[robot]: https://openjfx.io/javadoc/12/javafx.graphics/javafx/scene/robot/Robot.html

<h3 style = "color: purple;">4. Serialization of unserializable class member</h3>
While transferring object through ObjectOutputStream and ObjectInputStream by sockets, it would throw exception if the object has a non-serializable field like Image, WritableImage, etc. In order to pass the object of Serializable class, the non-serializable field must be declared transient.
{% highlight liquid%}
{% raw %}
{% highlight javascript %}
private transient Image image;
{% endhighlight %}
{% endraw %}
{%endhighlight%}
Moreover, one has to override the writeObject() and readObject() methods. Following are these for Image objects:
{% highlight liquid%}
{% raw %}
{% highlight javascript %}
private void readObject(ObjectInputStream s) throws IOException,
   ClassNotFoundException {
      s.defaultReadObject();
      this.image = SwingFXUtils.toFXImage(ImageIO.read(s),null);
}

private void writeObject(ObjectOutputStream s) throws IOException {
      s.defaultWriteObject();
      ImageIO.write(SwingFXUtils.fromFXImage(image, null),"png",s);
      s.flush();
}
{% endhighlight %}
{% endraw %}
{%endhighlight%}

<h3 style = "color: purple;">5. Updating GUI using Platform.runLater()</h3>
The Platform.runLater() runs on the main thread inside a Runnable.
{% highlight liquid%}
{% raw %}
{% highlight javascript %}
new Runnable(){
  @Override
  public void run(){
    // changes received...

    Platform.runLater(() -> {
      // update GUI here...
    });
  }
};
{% endhighlight %}
{% endraw %}
{%endhighlight%}
