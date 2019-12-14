## Goal

The goal of this project is to implement various keypoint detectors and descriptors and evaluate its performance on a series of camera images taken from the self driving car. 

On the basis of the analysis (processing time and matching efficiency) finally suggest the best combination of detectors and descriptors which can be used for this use case.

It consists of four parts:

* First, the focus is on loading images, setting up data structures and putting everything into a ring buffer to optimize memory load. 
* Then, several keypoint detectors such as HARRIS, FAST, BRISK and SIFT are integrated and compared with regards to number of keypoints and speed. 
* In the next part, the focus is on descriptor extraction and matching using brute force and also the FLANN approach
* In the last part, once the code framework is complete, various algorithms are tested in different combinations and compared with regard to some performance measures. 


## Performance Evaluation


#### MP.7 Different Detectors and number of keypoints detected


<table>
  <tr>
   <td><strong>Image Index</strong>
   </td>
   <td><p style="text-align: right">
<strong>0</strong></p>

   </td>
   <td><p style="text-align: right">
<strong>1</strong></p>

   </td>
   <td><p style="text-align: right">
<strong>2</strong></p>

   </td>
   <td><p style="text-align: right">
<strong>3</strong></p>

   </td>
   <td><p style="text-align: right">
<strong>4</strong></p>

   </td>
   <td><p style="text-align: right">
<strong>5</strong></p>

   </td>
   <td><p style="text-align: right">
<strong>6</strong></p>

   </td>
   <td><p style="text-align: right">
<strong>7</strong></p>

   </td>
   <td><p style="text-align: right">
<strong>8</strong></p>

   </td>
   <td><p style="text-align: right">
<strong>9</strong></p>

   </td>
   <td><strong>Average</strong>
   </td>
  </tr>
  <tr>
   <td>AKAZE
   </td>
   <td><p style="text-align: right">
166</p>

   </td>
   <td><p style="text-align: right">
157</p>

   </td>
   <td><p style="text-align: right">
161</p>

   </td>
   <td><p style="text-align: right">
155</p>

   </td>
   <td><p style="text-align: right">
163</p>

   </td>
   <td><p style="text-align: right">
164</p>

   </td>
   <td><p style="text-align: right">
173</p>

   </td>
   <td><p style="text-align: right">
175</p>

   </td>
   <td><p style="text-align: right">
177</p>

   </td>
   <td><p style="text-align: right">
179</p>

   </td>
   <td><p style="text-align: right">
<strong>167</strong></p>

   </td>
  </tr>
  <tr>
   <td>BRISK
   </td>
   <td><p style="text-align: right">
264</p>

   </td>
   <td><p style="text-align: right">
282</p>

   </td>
   <td><p style="text-align: right">
282</p>

   </td>
   <td><p style="text-align: right">
277</p>

   </td>
   <td><p style="text-align: right">
297</p>

   </td>
   <td><p style="text-align: right">
279</p>

   </td>
   <td><p style="text-align: right">
289</p>

   </td>
   <td><p style="text-align: right">
272</p>

   </td>
   <td><p style="text-align: right">
266</p>

   </td>
   <td><p style="text-align: right">
254</p>

   </td>
   <td><p style="text-align: right">
<strong>276.2</strong></p>

   </td>
  </tr>
  <tr>
   <td>FAST
   </td>
   <td><p style="text-align: right">
149</p>

   </td>
   <td><p style="text-align: right">
152</p>

   </td>
   <td><p style="text-align: right">
150</p>

   </td>
   <td><p style="text-align: right">
155</p>

   </td>
   <td><p style="text-align: right">
149</p>

   </td>
   <td><p style="text-align: right">
149</p>

   </td>
   <td><p style="text-align: right">
156</p>

   </td>
   <td><p style="text-align: right">
150</p>

   </td>
   <td><p style="text-align: right">
138</p>

   </td>
   <td><p style="text-align: right">
143</p>

   </td>
   <td><p style="text-align: right">
<strong>149.1</strong></p>

   </td>
  </tr>
  <tr>
   <td>HARRIS
   </td>
   <td><p style="text-align: right">
0</p>

   </td>
   <td><p style="text-align: right">
0</p>

   </td>
   <td><p style="text-align: right">
0</p>

   </td>
   <td><p style="text-align: right">
0</p>

   </td>
   <td><p style="text-align: right">
0</p>

   </td>
   <td><p style="text-align: right">
0</p>

   </td>
   <td><p style="text-align: right">
0</p>

   </td>
   <td><p style="text-align: right">
0</p>

   </td>
   <td><p style="text-align: right">
0</p>

   </td>
   <td><p style="text-align: right">
0</p>

   </td>
   <td><p style="text-align: right">
<strong>0</strong></p>

   </td>
  </tr>
  <tr>
   <td>ORB
   </td>
   <td><p style="text-align: right">
92</p>

   </td>
   <td><p style="text-align: right">
102</p>

   </td>
   <td><p style="text-align: right">
106</p>

   </td>
   <td><p style="text-align: right">
113</p>

   </td>
   <td><p style="text-align: right">
109</p>

   </td>
   <td><p style="text-align: right">
125</p>

   </td>
   <td><p style="text-align: right">
130</p>

   </td>
   <td><p style="text-align: right">
129</p>

   </td>
   <td><p style="text-align: right">
127</p>

   </td>
   <td><p style="text-align: right">
128</p>

   </td>
   <td><p style="text-align: right">
<strong>116.1</strong></p>

   </td>
  </tr>
  <tr>
   <td>SHITOMASI
   </td>
   <td><p style="text-align: right">
125</p>

   </td>
   <td><p style="text-align: right">
118</p>

   </td>
   <td><p style="text-align: right">
123</p>

   </td>
   <td><p style="text-align: right">
120</p>

   </td>
   <td><p style="text-align: right">
120</p>

   </td>
   <td><p style="text-align: right">
113</p>

   </td>
   <td><p style="text-align: right">
114</p>

   </td>
   <td><p style="text-align: right">
123</p>

   </td>
   <td><p style="text-align: right">
111</p>

   </td>
   <td><p style="text-align: right">
112</p>

   </td>
   <td><p style="text-align: right">
<strong>117.9</strong></p>

   </td>
  </tr>
  <tr>
   <td>SIFT
   </td>
   <td><p style="text-align: right">
138</p>

   </td>
   <td><p style="text-align: right">
132</p>

   </td>
   <td><p style="text-align: right">
124</p>

   </td>
   <td><p style="text-align: right">
137</p>

   </td>
   <td><p style="text-align: right">
134</p>

   </td>
   <td><p style="text-align: right">
140</p>

   </td>
   <td><p style="text-align: right">
137</p>

   </td>
   <td><p style="text-align: right">
148</p>

   </td>
   <td><p style="text-align: right">
159</p>

   </td>
   <td><p style="text-align: right">
137</p>

   </td>
   <td><p style="text-align: right">
<strong>138.6</strong></p>

   </td>
  </tr>
</table>


BRISK and ORB seems to have the maximum density of keypoints.

BRISK Detector Results

![alt_text](images/brisk_detector_results.png "image_tooltip")


ORB Detector Results


![alt_text](images/ORB_Detector_Results.png "image_tooltip")



#### MP.8 Number of Matches for all Detector/Descriptor combination


<table>
  <tr>
   <td>
   </td>
   <td><strong>BRIEF</strong>
   </td>
   <td><strong>ORB</strong>
   </td>
   <td><strong>FREAK</strong>
   </td>
   <td><strong>AKAZE</strong>
   </td>
   <td><strong>SIFT</strong>
   </td>
   <td><strong>BRISK</strong>
   </td>
  </tr>
  <tr>
   <td><strong>AKAZE</strong>
   </td>
   <td><p style="text-align: right">
108</p>

   </td>
   <td><p style="text-align: right">
131</p>

   </td>
   <td><p style="text-align: right">
126</p>

   </td>
   <td><p style="text-align: right">
138</p>

   </td>
   <td><p style="text-align: right">
134</p>

   </td>
   <td><p style="text-align: right">
126</p>

   </td>
  </tr>
  <tr>
   <td><strong>BRISK</strong>
   </td>
   <td><p style="text-align: right">
138</p>

   </td>
   <td><p style="text-align: right">
162</p>

   </td>
   <td><p style="text-align: right">
160</p>

   </td>
   <td><p style="text-align: right">
NA</p>

   </td>
   <td><p style="text-align: right">
182</p>

   </td>
   <td><p style="text-align: right">
138</p>

   </td>
  </tr>
  <tr>
   <td><strong>FAST</strong>
   </td>
   <td><p style="text-align: right">
97</p>

   </td>
   <td><p style="text-align: right">
118</p>

   </td>
   <td><p style="text-align: right">
98</p>

   </td>
   <td><p style="text-align: right">
NA</p>

   </td>
   <td><p style="text-align: right">
118</p>

   </td>
   <td><p style="text-align: right">
80</p>

   </td>
  </tr>
  <tr>
   <td><strong>HARRIS</strong>
   </td>
   <td><p style="text-align: right">
0</p>

   </td>
   <td>
   </td>
   <td><p style="text-align: right">
0</p>

   </td>
   <td><p style="text-align: right">
NA</p>

   </td>
   <td><p style="text-align: right">
0</p>

   </td>
   <td><p style="text-align: right">
0</p>

   </td>
  </tr>
  <tr>
   <td><strong>ORB</strong>
   </td>
   <td><p style="text-align: right">
37</p>

   </td>
   <td><p style="text-align: right">
67</p>

   </td>
   <td><p style="text-align: right">
42</p>

   </td>
   <td><p style="text-align: right">
NA</p>

   </td>
   <td><p style="text-align: right">
67</p>

   </td>
   <td><p style="text-align: right">
60</p>

   </td>
  </tr>
  <tr>
   <td><strong>SHITOMASI</strong>
   </td>
   <td><p style="text-align: right">
95</p>

   </td>
   <td><p style="text-align: right">
106</p>

   </td>
   <td><p style="text-align: right">
86</p>

   </td>
   <td><p style="text-align: right">
NA</p>

   </td>
   <td><p style="text-align: right">
112</p>

   </td>
   <td><p style="text-align: right">
84</p>

   </td>
  </tr>
  <tr>
   <td><strong>SIFT</strong>
   </td>
   <td><p style="text-align: right">
64</p>

   </td>
   <td><p style="text-align: right">
NA</p>

   </td>
   <td><p style="text-align: right">
65</p>

   </td>
   <td><p style="text-align: right">
NA</p>

   </td>
   <td><p style="text-align: right">
82</p>

   </td>
   <td><p style="text-align: right">
57</p>

   </td>
  </tr>
</table>



#### MP.9 Time for Keypoint Detection


<table>
  <tr>
   <td><strong>AKAZE</strong>
   </td>
   <td><strong>BRISK</strong>
   </td>
   <td><strong>FAST</strong>
   </td>
   <td><strong>HARRIS</strong>
   </td>
   <td><strong>ORB</strong>
   </td>
   <td><strong>SHITOMASI</strong>
   </td>
   <td><strong>SIFT</strong>
   </td>
  </tr>
  <tr>
   <td><p style="text-align: right">
79.09</p>

   </td>
   <td><p style="text-align: right">
140.145</p>

   </td>
   <td><p style="text-align: right">
1.56</p>

   </td>
   <td><p style="text-align: right">
13.8</p>

   </td>
   <td><p style="text-align: right">
36.16</p>

   </td>
   <td><p style="text-align: right">
11.28</p>

   </td>
   <td><p style="text-align: right">
72.92</p>

   </td>
  </tr>
</table>


Time for Description Extraction


<table>
  <tr>
   <td><strong>BRISK</strong>
   </td>
   <td><strong>ORB</strong>
   </td>
   <td><strong>FREAK</strong>
   </td>
   <td><strong>AKAZE</strong>
   </td>
   <td><strong>SIFT</strong>
   </td>
   <td><strong>BRISK</strong>
   </td>
  </tr>
  <tr>
   <td><p style="text-align: right">
4.09</p>

   </td>
   <td><p style="text-align: right">
1.55</p>

   </td>
   <td><p style="text-align: right">
27.16</p>

   </td>
   <td><p style="text-align: right">
44.5</p>

   </td>
   <td><p style="text-align: right">
25.16</p>

   </td>
   <td><p style="text-align: right">
1.43</p>

   </td>
  </tr>
</table>



## Final Analysis

**BRISK/SIFT** - For maximum number of matches

**FAST/ORB** - For good enough matches and total time to be very fast.

**SHITOMASI/ORB** - Next best number of matches and the total time to be fast.

## Dependencies for Running Locally
* cmake >= 2.8
  * All OSes: [click here for installation instructions](https://cmake.org/install/)
* make >= 4.1 (Linux, Mac), 3.81 (Windows)
  * Linux: make is installed by default on most Linux distros
  * Mac: [install Xcode command line tools to get make](https://developer.apple.com/xcode/features/)
  * Windows: [Click here for installation instructions](http://gnuwin32.sourceforge.net/packages/make.htm)
* OpenCV >= 4.1
  * This must be compiled from source using the `-D OPENCV_ENABLE_NONFREE=ON` cmake flag for testing the SIFT and SURF detectors.
  * The OpenCV 4.1.0 source code can be found [here](https://github.com/opencv/opencv/tree/4.1.0)
* gcc/g++ >= 5.4
  * Linux: gcc / g++ is installed by default on most Linux distros
  * Mac: same deal as make - [install Xcode command line tools](https://developer.apple.com/xcode/features/)
  * Windows: recommend using [MinGW](http://www.mingw.org/)

## Basic Build Instructions

1. Clone this repo.
2. Make a build directory in the top level directory: `mkdir build && cd build`
3. Compile: `cmake .. && make`
4. Run it: `./2D_feature_tracking`.

<!-- Docs to Markdown version 1.0β17 -->
