# EWO

EWO is a smart assistant that can not only hear but also see you. By taking inputs from a camera, EWO can take visual cues as well as audio cues. This means that an audio query can be further enhanced using the cotext given by an image.

## Example use case

In a clothes store, a user can hold up a dress, and ask the assistant if the dress is available in a different size. EWO can recognize the dress in the user's hand, and check availability of the required size in the store's database.

## functionality

The system is woken by the use of a special wakeword. Wakeword recognition is processed localy.

Once a wakeword is detected, the user's voice command is processed using an online natural language processing API. The keywords in the query are returned.

The device takes an image from the camera and uses posenet, a neural network which identifies the pose of a person, to identify the right hand of the user and crop an area around the right hand to recognize the object in the user's hand.

The resulting image is processed by a custom neural network trained on the inventory of the store, which identifies the item.

The item name and keywords from the user's query are combined, and the system uses the store's database to find the answer to the query.

The system answers the query through voice.



## current status

Planning to do hotword recognition using the snowboy library.

Image cropping network has been implemented using python. We are currently porting this functionality to the javascript version of posenet in order to use a node server for the system.


## Planned updates

#### Recognizing objects that the user points at.
train a 2nd nerual network to identify objects that the user points at.

#### Implementing classification of image classes (types of dogs, celeberities from a movie etc) by dynamically retraining a nerual network for classification.
If the user shows the assistant a picture of a dog, and asks "what type of dog is this?", the system should perform a google search for "types of dogs", download images for each of the top dog categories, retrain the last layer of a neural network for distiguishing between the downloaded image classes, and use the network to classify the original image.

## Automation challenge team members

Haritha Jayasinghe
Thameera Lakshan
