# Effi-ProPainter
Effi-ProPainter is an optimized version of the original ProPainter, enhancing GPU VRAM efficiency and enabling inference at higher parameter settings without encountering out-of-memory (OOM) issues. Effi-ProPainter uses only approximately 53% of the peak GPU VRAM consumption compared to the original ProPainter.

## Installation
The basic setup and installation procedures are identical to those of the original [ProPainter](https://github.com/sczhou/ProPainter).

1. Clone Repo

   ```bash
   git clone https://github.com/kimx3966/Effi-ProPainter.git
   ```

2. Create Conda Environment and Install Dependencies

   ```bash
   # create new anaconda env
   conda create -n propainter python=3.8 -y
   conda activate propainter

   # install python dependencies
   pip3 install -r requirements.txt
   ```

   - CUDA >= 9.2
   - PyTorch >= 1.7.1
   - Torchvision >= 0.8.2
   - Other required packages in `requirements.txt`


## Inference
Run the following commands to try it out:
```shell
# The first example (object removal)
python inference_effi_propainter.py --video inputs/object_removal/bmx-trees --mask inputs/object_removal/bmx-trees_mask 
# The second example (video completion)
python inference_effi_propainter.py --video inputs/video_completion/running_car.mp4 --mask inputs/video_completion/mask_square.png --height 240 --width 432
```

## License
Please be aware that ProPainter is governed by the non-commercial [S-Lab license](https://github.com/sczhou/ProPainter/blob/main/LICENSE).

## Acknowledgement
This implementation is built upon [ProPainter](https://github.com/sczhou/ProPainter). Huge thanks to the original authors for their impressive contribution!