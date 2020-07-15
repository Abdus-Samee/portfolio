---
title: JavaFX Snippets
tags:
 - code
 - syntax highlighting
---

I am currently doing some projects on JavaFX. Here in this blog, I've tried to gather some short queries I've had while doing these projects. These codes have been collected from the Internet and work perfectly. So to speak, these are mere code snippets, not a whole working code or package.

<!--more-->


<h3 style = "color: purple;">1. Converting java.awt BufferedImage to javafx.scene.image.Image</h3>
Here, we pass the BufferedImage `bufferedImage` as a parameter to the toFXImage method of SwingFXUtils class. It returns an `javafx.scene.image.Image` type object. If you use IntellIJ, then automatic import suggestions will appear.

{% highlight javascript %}
Image image = SwingFXUtils.toFXImage(bufferedImage, null);
{% endhighlight %}

<h3 style = "color: purple;">2. Converting WritableImage to javafx.scene.image.Image</h3>
We can save a WritableImage `writableImage` as an image file with `ImageIO.write()` method. The path of the file (`filePath`) just has to be mentioned. We can also pass an OutputStream as the third parameter.

{% highlight javascript %}
ImageIO.write(SwingFXUtils.fromFXImage(writableImage, null), "png", new File(filePath));
{% endhighlight %}


<h3 style = "color: purple;">3. Working with javafx.robot.Robot</h3>
In order to use this class, one should have JavaFX - 11 or higher. I prefer to use the higher ones. Besides, the robot object can work only in the main event thread. One cannot use this in other threads, because it will throw Exception. Below, is a declaration of Robot object.

{% highlight javascript %}
Robot robot = new Robot();
{% endhighlight %}

More info about [Robot][robot] class.

[robot]: https://openjfx.io/javadoc/12/javafx.graphics/javafx/scene/robot/Robot.html

<h3 style = "color: purple;">4. Serialization of unserializable class member</h3>
While transferring object through ObjectOutputStream and ObjectInputStream by sockets, it would throw exception if the object has a non-serializable field like Image, WritableImage, etc. In order to pass the object of Serializable class, the non-serializable field must be declared transient.

{% highlight javascript %}
private transient Image image;
{% endhighlight %}

Moreover, one has to override the writeObject() and readObject() methods. Following are these for Image objects:

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


<h3 style = "color: purple;">5. Updating GUI using Platform.runLater()</h3>
The Platform.runLater() runs on the main thread inside a Runnable.

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


<h3 style = "color: purple;">6. Working with `javafx.animation.Timeline` class</h3>
At first, the `Timeline` class is created with a preceeding `final` keyword as it immutable.
{% highlight javascript%}
      final Timeline timeline = new Timeline();
{%endhighlight%}
Then we create a `KeyValue` to be executred inside a `KeyFrame`. Remember, a single keyframe can hold multiple keyvalues to be occured at the same time. Keyvalues are those which mainly change the property. Keyframes are executed inside the timeline. A timeline can hold multiple keyframe childs.
{% highlight javascript%}
      final KeyValue kv = new KeyValue(initialProperty, finalProperty, Interpolator);
      final KeyFrame kf = new KeyFrame(Duration, list of keyframes);
      timeline.getKeyFrames().add(kf);
{%endhighlight%}


<h3 style = "color: purple;">7. Line drawing animation</h3>
Here, we show on the stage that the line is being drawn with the help of `Timeline` class. Otherwise, we usually draw a line with `Line` class which just puts the line on the stage, but doesn't show the drawing on the go.
We at first create the line as a point as follows. We must not forget to add the line as a child to the main container like, `anchorPane` in this case.
{% highlight javascript%}
      Line line = new Line();
      line.setStartX(100.0);
      line.setStartY(100.0);
      line.setEndX(100.0);
      line.setEndY(100.0);
      line.setStroke(Color.RED);
      anchorPane.getChildren().add(line);
{%endhighlight%}
Then we create the animation below with the endXProperty() increasing. Think why is it so.
{% highlight javascript%}
      final KeyValue kv = new KeyValue(line.endXProperty(), 400, Interpolator.EASE_IN);
      final KeyFrame kf = new KeyFrame(Duration.seconds(2.0), kv);
      timeline.getKeyFrames().add(kf);
      timeline.play();
{% endhighlight %}


<h3 style = "color: purple;">8. Circle drawing animation</h3>
We use the `Arc` class in order to draw a circle on the go with `Timeline` class. We change the `lengthProperty()` of the arc in animation. The circle only has a red-colored perimeter and so it is filled transparently.
{% highlight javascript %}
      Arc arc = new Arc(100.0, 100.0, 20.0, 20.0, 0.0, 0.0);
      arc.setFill(Color.TRANSPARENT);
      arc.setStroke(Color.RED);
{% endhighlight %}
Then the animation is usually the same as line animation.
{% highlight javascript %}
      final KeyValue kv = new KeyValue(arc.lengthProperty(), 380.0);
      final KeyFrame kf = new KeyFrame(Duration.seconds(2.0), kv);
      timeline.getKeyFrames().add(kf);
      timeline.play();
{% endhighlight %}
