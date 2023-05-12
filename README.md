# Smart City

## Requirements
- Docker
- Git (Optional, only if you want to clone this repository)

## How to Run
1. Download this repository or clone it with Git:
```
git clone https://github.com/widya-robotics-ai-intern-2023/smart_city.git
```
1. Download the model weights [here](https://drive.google.com/drive/folders/1gVZqc17D76PemjNEqF6qz4VILmhFCFRJ?usp=share_link) and move it to the **./model_weights/** folder.
2. To run the application, simply enter the following command in your terminal:
```
docker-compose up
```
1. To try the demo, open the API Docs (Swagger) by visiting to http://localhost:3000/docs.

## Demo
1. Open the API Docs (Swagger) by visiting to http://localhost:3000/docs.
2. Go to section **/camera/video (POST)** to upload the video that you want to stream and specify the parameters for the streamed video. You will need to include the following parameters in your request:

- **video**: the video file you want to stream
- **res**: the desired resolution for the video
- **loop**: whether or not the video should loop
- **counter_line_str**: an array of coordinate pairs to specify a counter line in the video

If the request is successful, the response will be as follows:

```
{
  "data": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "source": "./uploads/videos/video-1234567890.mp4",
    "res": 720,
    "loop": true,
    "counter_line": [
      [
        100,
        400
      ],
      [
        720,
        250
      ]
    ]
  }
}
```
3. To stream the video, use the "id" value returned in the successful response from step 2 as part of the URL http://localhost:3000/streams/{id}.