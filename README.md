
# Crime Detection using Machine-Learning
Crime Detection using Machine Learning and web3 is a project that aims to detect criminal activities in video footage using machine learning techniques and store the information in a database using django and web3 as auth.



## Installation


 Download or clone the repository
```bash
  git clone https://github.com/A-Akhil/Crime-Detection-using-Machine-Learning.git
  cd Crime-Detection-using-Machine-Learning-and-web3
```
Now install the dependencies for web3

```bash
  pip install -r requirement.txt
  pip install web3_auth_django-0.7-py3-none-any.whl
```
If you face any issues while installing web3_auth_django refer this [repo](https://github.com/ahn1305/web3-django-authentication)

And then install python dependencies

```bash
  pip install -r requirement-main.txt
```

Download the pre-trained models and video from Google Drive.
```bash
https://bit.ly/40m9Ka4
```
Extract the files and place them in the root directory of the project.

# To run in Docker

First build the Docker file
```
sudo docker build -t crime-detection .
```
Cerify the image was created
```
docker images
```
You should see something like this
```
crime-detection-app          latest     c7b090dc63   3 days ago      1.22GB
```
You can then run the container by
```
sudo docker run crime-detection
```
And then open http://127.0.0.1:8000/api in browser to access the web interface.

## Demo
Run the following command

Start the server:
```
python manage.py runserver
```
Make sure you install Metamask in

Open http://127.0.0.1:8000/api in browser to access the web interface.

Replace video4.mp4 with your video in main.py
```
# Load the video
vid = imageio.get_reader('video4.mp4',  'ffmpeg')
cap = cv2.VideoCapture('video4.mp4')
```

Now run:
```
python main.py
```

To check every frame in a video run
```
python all_frame_check.py
```

To run multiple video run
```
python multiple_video.py
```

Check the result in the website


<div align="center">

## Please support the development by donating.

[![BuyMeACoffee](https://img.shields.io/badge/Buy%20Me%20a%20Coffee-ffdd00?style=for-the-badge&logo=buy-me-a-coffee&logoColor=black)](https://buymeacoffee.com/aakhil)

</div>
