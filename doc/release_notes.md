OpenPose Library - Release Notes
====================================



## OpenPose 1.0.0rc1
1. Initial version, main functionality:
    1. Body keypoint detection and rendering on Ubuntu 14 and 16.
    2. It can read an image directory, video or webcam.
    3. It can display the results or storing them on disk.



## OpenPose 1.0.0rc2
1. Main improvements:
    1. Rendering max resolution from 720p to >32k images.
    2. Highly improved documentation.
2. Functions or parameters renamed:
    1. Demo renamed from rtpose to openpose.
3. Main bugs fixed:
    1. Demo uses exec instead of start, so it works with more OpenCV custom compiled versions.



## OpenPose 1.0.0rc3
1. Main improvements:
    1. Added face keypoint detection.
    2. Added Windows 10 compatibility.
    3. Auto-detection of the number of GPUs.
    4. MPI visualization more similar to COCO one.
    5. Rendering max resolution from 720p to >32k images.
    6. GUI info adder working when the worker TDatum has more than 1 Datum.
    7. It prints out the error description before throwing the exception (so that it is written on the Windows cmd).
    8. Highly improved documentation.
2. Functions or parameters renamed:
    1. Flag `write_pose` renamed as `write_keypoint` and it also applies to face and/or hands.
    2. Flag `write_pose_json` renamed as `write_keypoint_json` and it also applies to face and/or hands.
    3. Flag `write_pose_format` renamed as `write_keypoint_format` and it also applies to face and/or hands.
    4. PoseSaver and its JSON variant renamed as KeypointSaver.
    5. PoseJsonCocoSaver renamed as CocoJsonSaver.
3. Main bugs fixed:
    1. All visualization functions moved to same thread, so it works with most OpenCV custom compiled versions.
    2. Fixed error on debug mode: `Too many resources requested for launch`.



## OpenPose 1.0.0
1. Main improvements:
    1. Windows branch merged to master branch.
    2. Face and hands use `Maximum` instead of `Nms`, since there is only 1 person / detection.
    3. Increased accuracy on multi-scale (added `Datum::scaleRatios` to save the relative scale ratio when multi-scale).
    4. Increased speed ~5% by adding CPU rendering (but GPU is the default rendering).
    5. Rendering colors modified, visually better results.
    6. Check() functions give more feedback.
    7. WCocoJsonSaver finished and removed its 3599-image limit.
    8. Added `camera_fps` so generated video will use that frame rate.
    9. Reduced the number of printed information messages. Default logging priority threshold increased to Priority::Max.
    10. Google flags to OpenPose configuration parameters reader moved from each demo to utilities/flagsToOpenPose.
    11. Nms classes do not use `numberParts` for `Reshape`, they deduce the value.
    12. Improved documentation.
2. Functions or parameters renamed:
    1. Render flags renamed in the demo in order to incorporate the CPU/GPU rendering.
    2. Keypoints saved in JSON files (`write_keypoint_json`) are now saved as `pose_keypoints`, `face_keypoints`, `hand_left_keypoints`, and `hand_right_keypoints`. They all were previously saved as `body_parts`.
3. Main bugs fixed:
    1. Fixed bug in Array::getConstCvMat() if mVolume=0, now returning empty cv::Mat.
    2. Fixed bug: `--process_real_time` threw error with webcam.
    3. Fixed bug: Face not working when input and output resolutions are different.
    4. Fixed some bugs that prevented debug version to run.
    5. Face saved in JSON files were called `body_parts`. Now they are called `face_keypoints`.



## Current version (future OpenPose 1.0.1)
1. No changes yet.
