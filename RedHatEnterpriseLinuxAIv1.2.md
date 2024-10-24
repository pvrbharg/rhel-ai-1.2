## Red Hat Enterprise Linux AI 1.2 Release

RHEL AI provides organizations with a process to develop enterprise applications on open source Large
Language Models (LLMs).

#### ABOUT THIS RELEASE

Red Hat Enterprise Linux AI version 1.2 includes various features for Large Language Model (LLM) fine-
tuning on the Red Hat and IBM produced Granite model. A customized model using the RHEL AI
workflow consisted of the following:

```
Install and launch a RHEL 9.4 instance with the InstructLab tooling.
```
```
Host information in a Git repository and interact with a Git-based taxonomy of the knowledge
you want a model to learn.
```
```
Run the end-to-end workflow of synthetic data generation (SDG), multi-phase training, and
benchmark evaluation.
```
```
Serve and chat with the newly fine-tuned LLM.
```
#### FEATURES AND ENHANCEMENTS

Red Hat Enterprise Linux AI version 1.2 includes various features for Large Language Model (LLM) fine-
tuning.

###### Installing

Red Hat Enterprise Linux AI is installable as a bootable image. This image contains various tooling for
interacting with RHEL AI. The image includes: Red Hat Enterprise Linux 9.4, Python version 3.11 and
InstructLab tools for model fine-tuning. For more information about installing Red Hat Enterprise Linux
AI, see Installation overview.

Red Hat Enterprise Linux AI version 1.2 continues installation options for bare metal, AWS and IBM
Cloud. You can see all the supported installation options on RHEL AI in "Installation feature tracker". For
more information about the hardware requirements for these platforms, see Red Hat Enterprise Linux AI
hardware requirements.

###### Installing RHEL AI on systems with AMD accelerators (Technology Preview)

On RHEL AI version 1.2, you can now install and deploy Red Hat Enterprise Linux AI on machines with
AMD accelerators as a technology preview. RHEL AI currently only supports AMD hardware on bare
metal and Azure. For more information about RHEL AI hardware requirements for AMD, see Red Hat
Enterprise Linux AI hardware requirements.

RHEL AI verion 1.2 currently does not provide a training profile for AMD hardware. You need to manually
configure your **config.yaml** file and add the proper training configurations for training on AMD. For the
documentation on how to manually configure your AMD training profile, see Configuring the training
profile for AMD accelerators (Technology preview).

###### Installing RHEL AI on Google Cloud Platform (GCP) (Technology Preview)

On RHEL AI version 1.2, you can now install and deploy Red Hat Enterprise Linux AI on Google Cloud

```
RED HAT ENTERPRISE LINUX AI 1.2
```

```
On RHEL AI version 1.2, you can now install and deploy Red Hat Enterprise Linux AI on Google Cloud
Platform (GCP) instances as a technology preview. For the documentation on installing Red Hat
Enterprise Linux AI on GCP, see Installing on Google Cloud Platform (GCP)
```
```
RHEL AI currently supports 8xA100 and 8xH100 accelerators on GCP instances for the full end-to-end
workflow. You can also serve LLMs provided by Red Hat for inferencing on GCP instances. For more
details on the RHEL AI hardware requirements for GCP, see Red Hat Enterprise Linux AI hardware
requirements. For more information about the support scope of Red Hat Technology Preview features,
see Technology Preview Features Support Scope.
```
###### Installing RHEL AI on Azure (Technology Preview)

```
You can now install and deploy Red Hat Enterprise Linux AI version 1.2 on Microsoft Azure as a
technology preview. For the documentation on installing Red Hat Enterprise Linux AI on Azure, see
Installing on Azure
```
```
RHEL AI currently supports 8xA100 and 8xH100 accelerators on Azure instances for the full end-to-end
workflow. You can also serve LLMs provided by Red Hat for inferencing on Azure instances. For more
details on the RHEL AI hardware requirements for AWS, see Red Hat Enterprise Linux AI hardware
requirements. For more information about the support scope of Red Hat Technology Preview features,
see Technology Preview Features Support Scope.
```
###### Building your RHEL AI environment

```
After installing Red Hat Enterprise Linux AI, you can set up your RHEL AI environment with the
InstructLab tools.
```
###### Initializing InstructLab

```
You can initialize and set up your RHEL AI environment by running the ilab config init command. This
command creates the necessary configurations for interacting with RHEL AI and fine-tuning models. It
also creates proper directories for your data files.
```
```
Hardware auto-detection
```
```
Red Hat Enterprise Linux AI version 1.2 now offers hardware auto-detection when initializing InstructLab.
The CLI prompts you to confirm if the auto-detection selected your hardware correctly, then it
automatically adds the training parameters to your config.yaml file. For more information about
hardware auto-detection, see the Initialize InstructLab documentation.
```
###### Downloading Large Language Models

```
You can download various Large Language Models (LLMs) provided by Red Hat to your RHEL AI
machine or instance. You can download these models from a Red Hat registry after creating and logging
in to your Red Hat registry account. For more information about the supported RHEL AI LLMs, see the
Downloading models documentation and the "Large Language Models (LLMs) technology preview
status".
```
```
The granite-8b-code-instruct and granite-8b-code-base code models are continuing in Technology
Preview on RHEL AI version 1.2. For more information about the support scope of Red Hat Technology
Preview features, see Technology Preview Features Support Scope.
```
###### Serving and chatting with models

```
Red Hat Enterprise Linux AI version 1.2 allows you to run a vLLM inference server on various LLMs. The
```
Red Hat Enterprise Linux AI 1.2 


vLLM tool is a memory-efficient inference and serving engine library for LLMs that is included in the
RHEL AI image. For more information about serving and chatting with models, see Serving and chatting
with the models documentation.

There are various networking endpoint customizations you can create on Red Hat Enterprise Linux AI.
Including creating a API endpoint for serving a model, setting up your machine as a inference server, and
various other options. For more information about these customizations, see Serving and chatting with
the models documentation.

###### Customizing a Large Language Model (LLM) on RHEL AI

Red Hat Enterprise Linux AI allows you to customize and fine-tune the **granite-7b-starter** base model
with the RHEL AI end-to-end workflow.

###### Running the end-to-end workflow on IBM Cloud

On Red Hat Enterprise Linux AI version 1.2, you can now use IBM cloud to customize the Granite model
and run the end-to-end InstructLab workflow. For more details on the RHEL AI end-to-end hardware
requirements for IBM Cloud, see Red Hat Enterprise Linux AI hardware requirements.

###### Adding knowledge data to a Granite LLM.

On Red Hat Enterprise Linux AI, you can customize your taxonomy tree so a model can learn domain-
specific information. You host your knowledge data in a Git repository and fine-tune a model with that
data. In the RHEL AI workflow, you create a **qna.yaml** file that includes questions and answers for the
model to learn. This file gets run through the synthetic data generation (SDG) process, training, and
evaluation, to then create a new LLM that contains the data from the Git repository and **qna.yaml** file.
For detailed documentation on how to create a knowledge markdown and YAML file, see Adding
knowledge to your taxonomy tree.

###### Synthetic Data Generation (SDG)

Red Hat Enterprise Linux AI includes the LAB enhanced method of synthetic data generation (SDG).
You can use the **qna.yaml** files with your own knowledge data to create hundreds of artifical datasets in
the SDG process. For more information about running the SDG process, see Generating a new dataset
with Synthetic data generation (SDG).

###### Training a model with your data

Red Hat Enterprise Linux AI includes the LAB enhanced method of multi-phase training: A fine-tuning
strategy where datasets are trained and evaluated in multiple phases to create the best possible model.
For more details on multi-phase training, see Training your data on the model.

Training with Fully Sharded Data Parallels (FSDP) CPU offloading

Red Hat Enterprise Linux AI version 1.2 now supports PyTorch’s Fully Sharded Data Parallels (FSDP)
tool. You can now use FSDP during your training runs on RHEL AI.

Continuing training runs

Red Hat Enterprise Linux AI version 1.2 now allows you to continue a training run that may have failed
during multi-phase training. You can continue a training run by running the **ilab model train** command
with the now supported **--training-journal** flag that points to a YAML file that was generated during a

```
RED HAT ENTERPRISE LINUX AI 1.2 RELEASE
```

```
prior multi-phase training run. This takes the training data that was already generated and continues
training using that data. For more details on continuing training, see Continuing a training run.
```
###### Benchmark evaluation

```
Red Hat Enterprise Linux AI includes the ability to run benchmark evaluations on the newly trained
models. On your trained model, you can evaluate how well the model knows the model you added with
the MMLU_BRANCH benchmark. For more details on benchmark evaluation, see Evaluating your new
model.
```
#### RED HAT ENTERPRISE LINUX AI FEATURE TRACKER

###### Installation feature tracker

```
Table Installation features
```
```
Feature
```
```
Installing on bare metal Generally available Generally available
```
```
Installing on AWS Generally available Generally available
```
```
Installing on IBM Cloud Generally available Generally available
```
```
Installing on GCP Not available Technology
preview
```
```
Installing on Azure Not available Technology
preview
```
###### Platform support feature tracker

```
Table End-to-end InstructLab workflow
```
```
Feature
```
```
Bare metal Generally available Generally available
```
```
AWS Generally available Generally available
```
```
IBM Cloud Not available Generally available
```
```
Google Cloud Platform Not available Technology
preview
```
```
Azure Not available Technology
preview
```
```
Table Inference serving LLMs
```
Red Hat Enterprise Linux AI 1.2 Release


```
Feature
```
```
Bare metal Generally available Generally available
```
```
AWS Generally available Generally available
```
```
IBM Cloud Generally available Generally available
```
```
Google Cloud Platform (GCP) Not available Technology
preview
```
```
Azure Not available Technology
preview
```
#### TECHNOLOGY PREVIEW FEATURE STATUS

###### Large Language Models (LLMs) technology preview status

Table LLM features

```
Feature 1.1 1.
```
```
granite-7b-starter Generally available Generally available
```
```
granite-7b-redhat-lab Generally available Generally available
```
```
granite-8b-code-instruct Technology
preview
```
```
Technology
preview
```
```
granite-8b-code-base Technology
preview
```
```
Technology
preview
```
```
mixtral-8x7B-instruct-v0-1 Generally available Generally available
```
```
prometheus-8x7b-v2.0 Generally available Generally available
```
#### KNOWN ISSUES

###### Auto detecting a machine L40S accelorators

On Red Hat Enterprise Linux AI version 1.2, if you are using a machine with L40S accelerators, the CLI
hardware auto detection displays that the L40S is the approxomite training profile for your system, even
though the profile is an exact match. The L40S training profile is the appropriate training profile for this
system.

###### The ilab model download command does not show progress bar

The 1.2 version of RHEL AI does not show the progress of downloading models onto your system. This

```
RED HAT ENTERPRISE LINUX AI 1.2 
```

```
The 1.2 version of RHEL AI does not show the progress of downloading models onto your system. This
issue will be fixed in a later version of RHEL AI.
```
###### GUI AMD technology preview installations

```
Red Hat Enterprise Linux AI version 1.2 currently does not support graphical based installation with the
technology previewed AMD ISOs. Ensure that the text parameter in your kickstart file is configured for
non-interactive installs. You can also pass inst.text in your shell during interactive installation to avoid an
install time crash.
```
###### Kdump over nfs

```
Red Hat Enterprise Linux AI version 1.2 does not support kdump over nfs without configuration. To use
this feature, run the following commands:
```
```
mkdir -p /var/lib/kdump/dracut.conf.d
echo "dracutmodules=''" > /var/lib/kdump/dracut.conf.d/99-kdump.conf
echo "omit_dracutmodules=''" >> /var/lib/kdump/dracut.conf.d/99-kdump.conf
echo "dracut_args --confdir /var/lib/kdump/dracut.conf.d --install /usr/lib/passwd --install
/usr/lib/group" >> /etc/kdump.conf
systemctl restart kdump
```
Red Hat Enterprise Linux AI 1.2
