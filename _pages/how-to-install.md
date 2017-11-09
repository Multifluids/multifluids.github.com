---
permalink: /license/
title: "Contact details and license"
excerpt: "Contact details and license."
layouts_gallery:
  - url: /assets/images/mm-layout-splash.png
    image_path: /assets/images/mm-layout-splash.png
    alt: "splash layout example"
  - url: /assets/images/mm-layout-single-meta.png
    image_path: /assets/images/mm-layout-single-meta.png
    alt: "single layout with comments and related posts"
  - url: /assets/images/mm-layout-archive.png
    image_path: /assets/images/mm-layout-archive.png
    alt: "archive layout example"
modified: 2017-01-24T09:40:33-05:00
## Contact details
---



The multifluid Fluidity/IC-Ferst code base is developed and used at a number of academic institutions across the UK, including <a href="http://www.imperial.ac.uk/">Imperial College London</a>, <a href="the%20University%20of%20Aberdeen">the University of Aberdeen</a> and <a href="http://www.lsbu.ac.uk/">London South Bank University</a>. The code is released under the <a href="http://www.gnu.org/licenses/old-licenses/lgpl-2.1.en.html">GNU Lesser Public License version 2.1</a>. Public releases are made at irregular intervals, with internal releases on a monthly cycle.<br>

<br>
To request access to the private development repository, or for further information, please contact the heads of the project, <a href="http://www.imperial.ac.uk/people/c.pain">Professor Christopher Pain</a> or <a href="http://www.imperial.ac.uk/people/m.d.jackson">Professor Matthew D. Jackson</a>.<br>
  <br>
<address>
Department of Earth Science and Engineering<br>
Royal School of Mines<br>
Prince Consort Road<br>
Imperial College London<br>
SW7 2BP<br>
</address>

## How to install


<p> IC-FERST is developed and run on Linux. To install on such machines it is necessary to install certain supporting software.</p>


The basic list of supporting software, and method of installation, is the same as for the <a href="http://fluidityproject.github.io">single phase Fluidity code</a>.

<h2> Installing on Ubuntu </h2>

This is the best supported operating system. Intructions to install the necessary packages using the system package managers are given <a href="https://github.com/FluidityProject/fluidity/wiki/FAQ%3A-How-do-I-install-Fluidity-on-Ubuntu-LTS%3F">here</a>. Once the fluidity-dev package has been installed, your system should be able to compile the IC-Ferst/ Multifluid Fluidity package, which may be downloaded at the foot of this page. 
The list of commands to get IC-FERST working is as follows:

-- First install the Fluidity dependencies
{% highlight bash %}
sudo apt-add-repository ppa:fluidity-core/ppa
sudo apt-get update
sudo apt-get install fluidity fluidity-dev
export PETSC_DIR=/usr/lib/petscdir/3.6.3
{% endhighlight %}

It can be downloaded from github with the following one-line command
{% highlight bash %}
mkdir ICFERST && cd ICFERST && git init && git remote add -t  master  -f origin git@github.com:Multifluids/icferst.git && git checkout master
{% endhighlight %}

-- Next Navigate to the root directory of your IC-FERST folder
{% highlight bash %}
cd IC-FERST-FOLDER/
./configure --enable-2d-adaptivity
make mp
{% endhighlight %}

<h2> Installing on other Linux systems </h2>

Although less well supported, the code has been found to run successfully on Red Hat and OpenSUSE systemd. A list of hints and tips for these and other systems may be found <a href="https://github.com/FluidityProject/fluidity/wiki/FAQs">here</a>.


