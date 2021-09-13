 # siamFCppwarp
## get sub window

```
 cv::Mat warp_matrix(2, 3, CV_32FC1);
	float M_13 = target.x  - original_sz / 2; 
	float M_23 = target.y  - original_sz / 2; 
	float M_11 = 1.0 * original_sz / model_sz;
	float M_22 = 1.0 * original_sz / model_sz; //float M_22 =original_sz / 1.0*(model_sz - 1);

	warp_matrix.at<float>(0, 0) = M_11;
	warp_matrix.at<float>(0, 1) = 0;
	warp_matrix.at<float>(0, 2) = M_13;
	warp_matrix.at<float>(1, 0) = 0;
	warp_matrix.at<float>(1, 1) = M_22;
	warp_matrix.at<float>(1, 2) = M_23;
	
	cv::Mat patch;
	cv::warpAffine(img, patch,	warp_matrix, cv::Size(crop_size, crop_size),	cv::INTER_LINEAR | cv::WARP_INVERSE_MAP,	cv::BORDER_CONSTANT,
		avg_chans);

```
#References 



      @inproceedings{xu2020siamfc++,
      title={SiamFC++: Towards Robust and Accurate Visual Tracking with Target Estimation Guidelines.},
      author={Xu, Yinda and Wang, Zeyu and Li, Zuoxin and Yuan, Ye and Yu, Gang},
      booktitle={AAAI},
      pages={12549--12556},
      year={2020}
    }





