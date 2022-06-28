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
## Contact details
---

The multifluid Fluidity/IC-Ferst code base is developed and used at a number of academic institutions across the UK, including <a href="http://www.imperial.ac.uk/">Imperial College London</a>, <a href="the%20University%20of%20Aberdeen">the University of Aberdeen</a>, <a href="https://www.qub.ac.uk/">Queen's University Belfast</a>, <a href="https://www.uc.edu/">University of Cincinnati</a> and <a href="http://www.lsbu.ac.uk/">London South Bank University</a>. The code is released under the <a href="https://www.gnu.org/licenses/agpl-3.0.en.html">GNU Affero Public License version 3.0</a>. Public releases are made at irregular intervals.<br>

To request access to the development repository, or to request further information, please contact the heads of the project: <a href="http://www.imperial.ac.uk/people/pablo.salinas">Dr Pablo Salinas</a>, <a href="http://www.imperial.ac.uk/people/c.pain">Professor Christopher Pain</a> or <a href="http://www.imperial.ac.uk/people/m.d.jackson">Professor Matthew D. Jackson</a>.<br>

<address>
Department of Earth Science and Engineering<br>
Royal School of Mines<br>
Prince Consort Road<br>
Imperial College London<br>
SW7 2BP<br>
</address>

## How to install
---
<p> IC-FERST is developed and run on Linux. To install on such machines it is necessary to install certain supporting software.</p>


The basic list of supporting software, and method of installation, is the same as for the <a href="http://fluidityproject.github.io">single phase Fluidity code</a>.

<h2> Installing on Ubuntu </h2>

This is the best supported operating system. Intructions to install the necessary packages using the system package managers are given <a href="https://github.com/FluidityProject/fluidity/wiki/FAQ%3A-How-do-I-install-Fluidity-on-Ubuntu-LTS%3F">here</a>. Once the fluidity-dev package has been installed, your system should be able to compile the IC-Ferst/ Multifluid Fluidity package, which may be downloaded at the foot of this page. 
The list of commands to get IC-FERST working is as follows:

Download it from github with the following one-line command
{% highlight bash %}
mkdir ICFERST && cd ICFERST && git init && git remote add -t  main  -f origin git@github.com:Multifluids/icferst.git && git checkout main
{% endhighlight %}

-- Install dependencies
{% highlight bash %}
sudo apt-add-repository ppa:fluidity-core/ppa
sudo apt-get update
sudo apt-get install fluidity-dev
{% endhighlight %}

-- Ubuntu 18.04, modify the .bashrc file in home to include
{% highlight bash %}
export PETSC_DIR=/usr/lib/petscdir/3.8.3
{% endhighlight %}

-- Ubuntu 20.04, modify the .bashrc file in home to include
{% highlight bash %}
export FCFLAGS="-I/usr/include"
{% endhighlight %}

You may need to explicitly include the python dependencies
{% highlight bash %}
export PYTHONPATH=/usr/lib/python3
{% endhighlight %}

-- Navigate to the root directory of your ICFERST folder
{% highlight bash %}
cd IC-FERST-FOLDER/
sudo ./configure --enable-2d-adaptivity && make install
{% endhighlight %}

<h2> Using the diamond GUI to configure test cases </h2>
The input files are "EXAMPLE.mpml". This files can be either manipulated using diamond a GUI, or a text file. To open the diamond GUI for ICFERST this is an example, found in the examples folder in IC-FERST-FOLDER/legacy_reservoir_prototype/tests/3D_BL
{% highlight bash %}
diamond -s IC-FERST-FOLDER/legacy_reservoir_prototype/schemas/multiphase.rng 3D_test.mpml
{% endhighlight %}


<h2> Installing on other Linux systems </h2>

Although less well supported, the code has been found to run successfully on Red Hat and OpenSUSE systemd. A list of hints and tips for these and other systems may be found <a href="https://github.com/FluidityProject/fluidity/wiki/FAQs">here</a>.


