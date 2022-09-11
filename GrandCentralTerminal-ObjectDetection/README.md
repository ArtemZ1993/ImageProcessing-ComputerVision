## Grand Central Terminal - ObjectDetection

Submitted by: Shay Malkin and Artem Zinenko 

Project video: Grand Central Station

Project objectives :

● To track hundreds of people walking around the station.

● To track people entering the station from different entrances and represent
them with different colors.

● To draw the people’s paths.
● To display a heat map of all the different paths in real time
The video shows hundreds of people walking through a busy central station.

With computer vision techniques we are able to track many individual people at the
same time as they walk around the station.
In the first frame of the video, we find key points to track using the Shi-Tomasi
Corner Detector .
Then, we loop through the rest of the frames, calculating the change in position of
each key point in each frame with regards to the previous frame. This is done with
the Lucas-Kanade Optical Flow algorithm. This allows us to draw a line between
every point and its corresponding one in the next frame.
The lines are drawn on a blank canvas with the same dimensions as the frames.
At each iteration, we draw the current segments of all the paths on the canvas.
Over the course of the video, the complete paths are drawn on that canvas.
The canvas is a black and white image. We pass it through a gaussian filter to
smooth it out. The result is a gray scale image that shows areas where many people
have passed in a brighter shade and the less frequently passed ones in darker
shades. Then we simply apply a color map and the result is a heat map of all the
paths.

The main problems we had with the project are:

● The ability to mark each person with only one point.
Often, the algorithm finds various points on the same person, resulting in a
false representation of a path. Instead of marking the path of one person, it
shows as if a few people walked that same path.
We tried to minimize this phenomenon by tweaking the parameters of the
corner detector.

● Key points “passing” from one person to another.
The main problem with this algorithm is that when people pass behind one
another (and this happens a lot in this particular video), they tend to “give”
their key points to one another. This obviously creates false paths because
the tracking point jumps from one person to another.
This is a major issue in tracking projects, though, there are ways around it.
These methods involve techniques way beyond the scope of this project.
LSTM neural networks, for example..
.
