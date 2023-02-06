# K8S Cluster Utilization Dashboard


The attached Grafana dashboard visualizes k8s resources usage and utilization based on Prometheus matrices. It allows you to get the big picture of your cluster utilization. It compares three key elements:
* Actual - The real usage of the workloads
* Requested - How many resources the pods requested
* Allocated - How many resources k8s and auto-scaling mechanism allocated (What you are paying for) 

This is how it looks like:
![PHOTO-2022-08-10-14-48-31](https://user-images.githubusercontent.com/51505354/216934790-17b3a43a-ed4f-4a36-8c75-228f7cb107c2.jpg)

  * The first two rows aggregate the average usage in the selected period.
  * Over-requesting: The difference between Actual to Requested is a waste caused by over-requesting too many resources.
  * Over-allocating: The difference between Requested to Allocated is a waste caused by over-allocating resources compared to what the DevOps teams requested to allocate.
  * Monthly wasted resources: The monthly vCPU cost varies between 10 to 30 dollars, depending on the machine, how much ram is required, the utilization of spot instances, reserved instances, and discounts from cloud providers. Calculating how much you pay for resources you don’t use is roughly multiplying 10$ (Assuming you maximize saving mechanisms and consume ram efficiently) by the amount of unused vCPU.
  * The last two panel rows visualize the utilization over time in absolute and average numbers

## Installation
Installing the dashboard takes a few minutes, as it is a standard Grafana dashboard:
Open import tab:
<img width="794" alt="CYJ8Zx-zQPdv_pDCqsx9MgmnFHsvg0TMP-1mEm_lm-9qpEo6MF6chR9O4dlDK-j-EInWBTxhSdD8ZQMBq5995quh8__fPY4ZpPX62_yufey8efRYkhz0a30IdJI0CQqS8wBHpgghUxydHlbtlK_TZPY" src="https://user-images.githubusercontent.com/51505354/216935960-f6e8ecfc-26f8-448d-9230-d56730c54940.png">

Upload the json as a file or paste it into the import panel, and press load
<img width="741" alt="N-9ZaQpT36MFB5xzCAH-DFG0tEMd_l9L4CdkRdNfgMliJpyRNtnb8wX_t6RbqF1P-BuzoJsjaw968jgmKbv7eHabbQJa5RJrpDa2hocsT8msX_uX8lJAaecbiLTcbqPr06dw17vJw6Uf50HX1m8KGP0" src="https://user-images.githubusercontent.com/51505354/216936032-f63b391e-84ae-4022-a7ac-01502450f3a6.png">


In the next tab, press import

![5BQkeCOCaXl0SHDlL85crC61cZWUn31h2xAwMrzKRM7yCSLmcl9X_M-6d9gQSnFni8OcMXWFrp6nqxVlsN6VZWEwWf8XvImVuM7aquhi0C93WdpJ4589DP-StP9gTMTqbm7pbWPr-YfpXbV-3LJpcAA (1)](https://user-images.githubusercontent.com/51505354/216936076-8b390115-019b-4c4f-9d95-e519a6b5fd55.png)
