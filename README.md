# RedditChatBot
A chat bot made from the reddit comments. You can ask it questions and it will reply with the best scoring answer.

# Get the data and prepare/filter it

* First get a file which is large enough, i used reddit comments dataset file from here : https://www.reddit.com/r/datasets/comments/3bxlg7/i_have_every_publicly_available_reddit_comment/?utm_source=reddit
. Run chatbot_database.py to convert the data into a sql database. This will pair all the rows and neatly prepare all the required files. Now run create_training_data.py so now we can create two data files, train.from and train.to. These are the 'parent' and 'reply' files which the nmt will learn with.

# Training Model

* Now for the training model, we will use nmt model which is tweaked a little bit from Daniel-kukiela. Follow the following commands:
```
$ git clone --recursive https://github.com/daniel-kukiela/nmt-chatbot
$ cd nmt-chatbot
$ pip install -r requirements.txt
$ cd setup
(optional) edit settings.py to your liking. These are a decent starting point for ~4gb of VRAM, you should first start by trying to raise vocab if you can.
(optional) Edit text files containing rules in setup directory
Place training data inside "new_data" folder (train.(from|to), tst2012.(from|to)m tst2013(from|to)). We have provided some sample data for those who just want to do a quick test drive.
$ python prepare_data.py ...Run setup/prepare_data.py - new folder called "data" will be created with prepared training data
$ cd ../
$ python train.py Begin training
```
You can check the progress of your training by cd into model and typing ```tensorboard --logdir=train_log/```

# Running the model
* To run the model, run inference.py in the main dir, ask the bot questions and it will reply with 10 answers. The green highlighted being the best scoring answer, and the red being the irrelevant and unusual. You can tweak the bot to only show the best answer but for testing purposes it is enabled by default.

# RECOMENDED
* It is highly recomended to train the model on a virtual machine from Google Cloud Platform or PaperSpace as it takes a lot of time for the model to train.

# Photos
* Uploaded some photos of progress
![Image 1](https://github.com/zohairajmal/RedditChatBot/blob/master/photos/IMG_1138.jpg)
![Image 2](https://github.com/zohairajmal/RedditChatBot/blob/master/photos/IMG_1139.jpg)
![Image 3](https://github.com/zohairajmal/RedditChatBot/blob/master/photos/IMG_1143.jpg)
![Image 4](https://github.com/zohairajmal/RedditChatBot/blob/master/photos/IMG_1144.jpg)
![Image 5](https://github.com/zohairajmal/RedditChatBot/blob/master/photos/IMG_1147.jpg)
![Image 6](https://github.com/zohairajmal/RedditChatBot/blob/master/photos/IMG_1148.jpg)
![Image 7](https://github.com/zohairajmal/RedditChatBot/blob/master/photos/IMG_1149.jpg)
![Image 8](https://github.com/zohairajmal/RedditChatBot/blob/master/photos/IMG_1164.jpg)
![Image 9](https://github.com/zohairajmal/RedditChatBot/blob/master/photos/IMG_1165.jpg)
![Image 10](https://github.com/zohairajmal/RedditChatBot/blob/master/photos/IMG_1166.jpg)
