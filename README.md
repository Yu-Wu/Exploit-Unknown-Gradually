# [Exploit the Unknown Gradually: One-Shot Video-Based Person Re-Identification by Stepwise Learning](https://yu-wu.net/pdf/CVPR2018_Exploit-Unknown-Gradually.pdf)

Pytorch implementation for our paper [[Link]](http://openaccess.thecvf.com/content_cvpr_2018/papers/Wu_Exploit_the_Unknown_CVPR_2018_paper.pdf).
This code is based on the [Open-ReID](https://github.com/Cysu/open-reid) library.

## Preparation
### Dependencies
- Python 3.6
- PyTorch (version >= 0.2.0)
- h5py, scikit-learn, metric-learn, tqdm

### Download datasets 
- DukeMTMC-VideoReID: This [page](https://github.com/Yu-Wu/DukeMTMC-VideoReID) contains more details and baseline code.
- MARS: [[Google Drive]](https://drive.google.com/open?id=1m6yLgtQdhb6pLCcb6_m7sj0LLBRvkDW0)   [[BaiduYun]](https://pan.baidu.com/s/1mByTdvXFsmobXOXBEkIWFw).
- Move the downloaded zip files to `./data/` and unzip here.


## Train

For the DukeMTMC-VideoReID dataset:
```shell
python3 run.py --dataset DukeMTMC-VideoReID --logs_dir logs/DukeMTMC-VideoReID_EF_10/ --EF 10 --mode Dissimilarity --max_frames 900
```

For the MARS datasaet:
```
python3 run.py --dataset mars --logs_dir logs/mars_EF_10/ --EF 10 --mode Dissimilarity --max_frames 900
```
It takes about 10 hours to train EUG (EF=10%) on DukeMTMC-VideoReID with a GTX1080Ti. Please set the `max_frames` smaller if your GPU memory is less than 11G.

## Performances

The performances varies according to random splits for initial labeled data. To reproduce the performances in our paper, please use the one-shot splits at `./examples/`


## Citation

Please cite the following paper in your publications if it helps your research:

    @inproceedings{wu2018cvpr_oneshot,
        title = {Exploit the Unknown Gradually: One-Shot Video-Based Person Re-Identification by Stepwise Learning},
        author = {Wu, Yu and Lin, Yutian and Dong, Xuanyi and Yan, Yan and Ouyang, Wanli and Yang, Yi},
        booktitle = {The IEEE Conference on Computer Vision and Pattern Recognition (CVPR)},
        year = {2018}
    }

## Future work

In the extended version,  We improve EUG by leveraging the remaining unselected data in an unsupervised way, which shows a great performance improvement on the image-based re-ID datasets (Market-1501 and DukeMTMC-reID). [[Paper]](https://yu-wu.net/pdf/TIP2019_One-Example-reID.pdf) [[Code]](https://github.com/Yu-Wu/One-Example-Person-ReID)

    
## Contact

To report issues for this code, please open an issue on the [issues tracker](https://github.com/Yu-Wu/Exploit-Unknown-Gradually/issues).

If you have further questions about this paper, please do not hesitate to contact me. 

[Yu Wu's Homepage](https://yu-wu.net)


