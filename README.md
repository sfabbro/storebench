storebench
==========

Suite of scripts to test storage systems for data processing.

The idea is to replicate a typical scientist using virtualization and
storage for unsupervised data processing. Typically the steps are:
* download input files from object storage to VM
* process the files with software stack on VM
* save results of processing to object storage
The above procedure is repeated as many times as jobs are scheduled.
In some situations (like federated geographically remote clusters),
there is no local storage for the results which are often temporary
data products and serve as inputs for the next processing batch jobs.

storebench tests reliability and performance of some storage
solutions, especially useful when hundreds of VMs are trying to access
the storage simultaneously. Implemented solutions are:
* rsync/ssh to a single private box (ssh)
* VOSpace client (vos)
* OpenStack swift (oss)

ex: storebench oss oss-10
