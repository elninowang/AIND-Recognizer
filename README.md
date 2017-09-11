# Artificial Intelligence Engineer Nanodegree
## Probabilistic Models 概率模型
## Project: Sign Language Recognition System 项目:手语识别系统

### Install 安装

This project requires **Python 3** and the following Python libraries installed:

- [NumPy](http://www.numpy.org/)
- [SciPy](https://www.scipy.org/)
- [scikit-learn](http://scikit-learn.org/0.17/install.html)
- [pandas](http://pandas.pydata.org/)
- [matplotlib](http://matplotlib.org/)
- [jupyter](http://ipython.org/notebook.html)
- [hmmlearn](http://hmmlearn.readthedocs.io/en/latest/)

Notes: 
1. It is highly recommended that you install the [Anaconda](http://continuum.io/downloads) distribution of Python and load the environment included in the "Your conda env for AI ND" lesson.
2. The most recent development version of hmmlearn, 0.2.1, contains a bugfix related to the log function, which is used in this project.  In order to install this version of hmmearn, install it directly from its repo with the following command from within your activated Anaconda environment:

笔记：
1. 强烈建议您安装Python的[Anaconda](http://continuum.io/downloads) 分发版，并载入"Your conda env for AI ND"课程中包含的环境。
2. 最近的开发版本hmmlearn，0.2.1包含与日志功能相关的修补程序，该修补程序在本项目中使用。 为了安装这个版本的hmmearn，可以通过从您的激活的Anaconda环境中的以下命令直接从其repo安装它：

```sh
pip install git+https://github.com/hmmlearn/hmmlearn.git
```

### Code 代码

A template notebook is provided as `asl_recognizer.ipynb`. The notebook is a combination tutorial and submission document.  Some of the codebase and some of your implementation will be external to the notebook. For submission, complete the **Submission** sections of each part.  This will include running your implementations in code notebook cells, answering analysis questions, and passing provided unit tests provided in the codebase and called out in the notebook. 

模板笔记本以 `asl_recognizer.ipynb` 提供。 笔记本是一个组合教程和提交文件。 一些代码库和一些实现将在笔记本电脑外部。 要提交，请填写每个部分的**提交** 部分。 这将包括在代码笔记本电脑中运行您的实现，回答分析问题，并传递提供的代码库中提供的单元测试并在笔记本中调出。

### Run 运行

In a terminal or command window, navigate to the top-level project directory `AIND_recognizer/` (that contains this README) and run one of the following command:

在终端或命令窗口中，导航到顶级项目目录 `AIND_recognizer/` （包含此README），并运行以下命令之一：

`jupyter notebook asl_recognizer.ipynb`

This will open the Jupyter Notebook software and notebook in your browser which is where you will directly edit and run your code. Follow the instructions in the notebook for completing the project.

这将在您的浏览器中打开Jupyter Notebook软件和笔记本，您将直接编辑和运行代码。 按照笔记本计算机中的说明完成项目。

### Additional Information 附加的信息
##### Provided Raw Data 提供原始数据

The data in the `asl_recognizer/data/` directory was derived from 
the [RWTH-BOSTON-104 Database](http://www-i6.informatik.rwth-aachen.de/~dreuw/database-rwth-boston-104.php). 
The handpositions (`hand_condensed.csv`) are pulled directly from 
the database [boston104.handpositions.rybach-forster-dreuw-2009-09-25.full.xml](boston104.handpositions.rybach-forster-dreuw-2009-09-25.full.xml). The three markers are:

`asl_recognizer/data/` 目录中的数据源自
[RWTH-BOSTON-104数据库](http://www-i6.informatik.rwth-aachen.de/~dreuw/database-rwth-boston-104.php)。
手指（`hand_condensed.csv`）直接从中拉出
数据库[boston104.handpositions.rybach-forster-dreuw-2009-09-25.full.xml](boston104.handpositions.rybach-forster-dreuw-2009-09-25.full.xml)。 三个标记是：

*   0  speaker's left hand 左手
*   1  speaker's right hand 右手
*   2  speaker's nose 鼻子
*   X and Y values of the video frame increase left to right and top to bottom. 视频帧的X和Y值从左到右和从上到下增加。

Take a look at the sample [ASL recognizer video](http://www-i6.informatik.rwth-aachen.de/~dreuw/download/021.avi)
to see how the hand locations are tracked.

看看样品 [ASL识别器视频](http://www-i6.informatik.rwth-aachen.de/~dreuw/download/021.avi)
以了解如何跟踪手的位置。

The videos are sentences with translations provided in the database.  
For purposes of this project, the sentences have been pre-segmented into words 
based on slow motion examination of the files.  
These segments are provided in the `train_words.csv` and `test_words.csv` files
in the form of start and end frames (inclusive).

视频是数据库中提供翻译的句子。
为了本项目的目的，根据文件的慢动作检查，这些句子已经被分段成了单词。
这些段以 `train_words.csv` 和 `test_words.csv` 文件的形式以开始和结束帧（包括）的形式提供。

The videos in the corpus include recordings from three different ASL speakers.
The mappings for the three speakers to video are included in the `speaker.csv` 
file.

语料库中的视频包括来自三个不同ASL音箱的录音。
三个演讲者到视频的映射包含在`speaker.csv`文件中。
