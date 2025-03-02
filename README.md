# Lunar
Lunar is a neural network aimbot that uses real-time object detection accelerated with CUDA on Nvidia GPUs.

## About

Lunar can be modified to work with a variety of FPS games; however, it is currently configured for Fortnite. Besides being general purpose, the main advantage of using Lunar is that it is virtually undetectable by anti-cheat software (no memory is meddled with).

The basis of Lunar's player detection is the [YOLOv5](https://github.com/ultralytics/yolov5) architecture written in the PyTorch framework.

A demo video (outdated) can be found [here](https://www.youtube.com/watch?v=XDAcQNUuT84).
![thumbnail](https://user-images.githubusercontent.com/45726273/126563920-193ca8df-de70-4a91-81ec-d781ee961332.png)

## Important Notice
I have sold a closed-source version of this project and will no longer be updating this repo. It is now being run by [Lunar Enhancements](https://www.lunarenhance.com).
## Installation

1. Install a version of [Python](https://www.python.org/downloads/) 3.8 or later.

2. Navigate to the root directory. Use the package manager [pip](https://pip.pypa.io/en/stable/) to install the necessary dependencies.

```
pip install -r requirements.txt
```

## Usage
```           
python lunar.py
```
To update sensitivity settings:
```           
python lunar.py setup
```
To collect image data for annotating and training:
```           
python lunar.py collect_data
```

## Issues
- The method of mouse movement ([SendInput](https://github.com/zeyad-mansour/Lunar/blob/45e05373036f8bd072667313c155e55735cd7f57/lib/aimbot.py#L126)) is slow. For this reason, the crosshair often lags behind a moving detection. This problem can be lessened by increasing the [pixel_increment](https://github.com/zeyad-mansour/Lunar/blob/45e05373036f8bd072667313c155e55735cd7f57/lib/aimbot.py#L56) (e.g. to 4) so fewer calls to that function are made.
- The model is trained on a dataset of Fortnite players, and it will not work well for other games. False positives can also happen under certain lighting conditions.
- There is a known issue that occurs with PyTorch and the GeForce 16 series GPUs on Windows. Unfortunately, if you are using one of these GPUs, the aimbot will not work for you.

## Future Updates
- [x] Train a model on a custom dataset
- [ ] Implement better player tracking
- [ ] Add support for other FPS games (e.g. Valorant, Warzone)
- [ ] Use TensorRT for faster inference
- [ ] Make an easy-to-use GUI

## Contributing
Pull requests are welcome. If you have any suggestions, questions, or find any issues, please open an [issue](https://github.com/zeyad-mansour/Lunar/issues) and provide some detail.
If you find this project interesting or helpful, please star the repository.
