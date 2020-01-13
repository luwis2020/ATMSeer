<p align="left">
<img width=15% src="https://dai.lids.mit.edu/wp-content/uploads/2018/06/Logo_DAI_highres.png" alt=“DAI-Lab” />
<i>An open source project from Data to AI Lab at MIT.</i>
</p>



# ATMSeer

ATMSeer is an interactive visualization tool for automated machine learning (AutoML). It supports users to monitor an ongoing AutoML process, analyze the searched models, and refine the search space in real-time through a multi-granularity visualization. In this instantiation, we build on top of the [ATM AutoML system](https://github.com/HDI-Project/ATM).

Our paper, "ATMSeer: Increasing Transparency and Controllability in Automated Machine Learning", was presented at CHI 2019 ([pdf](https://arxiv.org/abs/1902.05009), [site](https://dai.lids.mit.edu/projects/atmseer/)).

[![ATMSEER VIDEO](https://img.youtube.com/vi/7QwN3mmiCzY/0.jpg)](http://www.youtube.com/watch?v=7QwN3mmiCzY "Video Title")

## Installation

### Prerequisites

Download and install or update [VirtualBox](https://www.virtualbox.org/wiki/Downloads) and [Vagrant](https://www.vagrantup.com/downloads.html).

### Download ATMSeer

```
git clone https://github.com/HDI-Project/ATMSeer.git

https://github.com/taowenyin/ATMSeerInitialization/blob/master/Book.md

```

### Install and launch

Then go to ATMSeer project from the terminal and run

```
sh install.sh
```

This will install all the necessary packages in a virtual environment and launch the ATMSeer server.

If you see these messages in terminal:

```
...
default: [INFO] [13:07:26:werkzeug]  * Running on http://0.0.0.0:7777/ (Press CTRL+C to quit)
default: [INFO] [13:07:26:werkzeug]  * Restarting with stat
default: [WARNING] [13:07:31:werkzeug]  * Debugger is active!
default: [INFO] [13:07:31:werkzeug]  * Debugger PIN: 295-249-971
default: No valid rules have been specified for JavaScript files

```
then ATMSeer is up and running.

Finally, navigate to `http://localhost:7779/` in your broswer (preferably Chrome) to see ATMSeer.

### Debugging

In case you experience any issues, please try the following.

1. Open a terminal and navigate to ATMSeer project location.
2. Run `vagrant up` command (in case vagrant is not already running).
3. From the same terminal run `vagrant ssh`.
4. Run `cd /vagrant` and `sh start.sh`.

Open a second terminal and navigate to the ATMSeer project directory.
Run `vagrant ssh`, `cd /vagrant`, and `npm start`.

If you are still experiencing issues, please [open an issue](https://github.com/HDI-Project/ATMSeer/issues/new) and include as much detail as you can on your problem.

### Deploy with Docker [alternative]

If you have problem using [VirtualBox](https://www.virtualbox.org/wiki/Downloads) and [Vagrant](https://www.vagrantup.com/downloads.html) (especially in Windows), you can choose to use Docker instead.

Download and Install [Docker](https://docs.docker.com/install/) and [Compose](https://docs.docker.com/compose/install/)

```
sh install-docker.sh
```

If you see the following message:

```
atmseer |  * Serving Flask app "server" (lazy loading)
atmseer |  * Environment: production
atmseer |    WARNING: Do not use the development server in a production environment.
atmseer |    Use a production WSGI server instead.
atmseer |  * Debug mode: off
atmseer | [INFO] [13:43:13:werkzeug]  * Running on http://0.0.0.0:5000/ (Press CTRL+C to quit)
```

You can navigate to `http://localhost:5000/` in your broswer (preferably Chrome) to see ATMSeer.



## Using ATMSeer

To see ATMSeer in action, you will first upload a dataset to use with the AutoML process, create a "datarun", and then monitor and control the ongoing AutoML process.

### Upload a dataset

You first need to upload a dataset to use with the AutoML process. We have provided several example datasets in `public/viz`. For example, press "Upload" and navigate to your ATMSeer installation and upload `public/viz/blood.csv`.

To use your own dataset, take care to provide it in the required data format (https://hdi-project.github.io/ATM/readme.html#data-format).

### Create a datarun

A datarun is a single AutoML process, comprising a dataset, a configuration for the AutoML process, and associated state information.

To create a new datarun, click the add icon, adjust methods, budget type, and budget, and press "Submit". You should not need to adjust advanced settings in most cases. If you do, please see https://hdi-project.github.io/ATM/database.html#dataruns for some details on the setting options.

### Start the AutoML process

Now, select your datarun from the list and press "Run" to begin the AutoML process. You should see completed trials populate on the top panel and details of algorithms, hyperpartitions, and hyperparameters in the three-level visualization on the right.

## Reference

If you use ATMSeer, please consider citing our paper:

``` bibtex
@inproceedings{wang2019atmseer,
  author = {Wang, Qianwen and Ming, Yao and Jin, Zhihua and Shen, Qiaomu and Liu, Dongyu and Smith, Micah J. and Veeramachaneni, Kalyan and Qu, Huamin},
  title = {ATMSeer: Increasing Transparency and Controllability in Automated Machine Learning},
  booktitle = {Proceedings of the 2019 CHI Conference on Human Factors in Computing Systems},
  series = {CHI '19},
  year = {2019},
  location = {Glasgow, Scotland UK},
  publisher = {ACM},
  address = {New York, NY, USA},
  url = {http://doi.acm.org/10.1145/3290605.3300911}
}
```
