# reboot
Rebooting instances inside ASG
There are two methods by which we could reboot the instances inside an ASG.
Either we could go to ASG > instance managment > Detach the instance from the ALB 
Now the instance is detached from the ASG and not a part of it anymore so there wont be any active monitoring on the instance. So if we reboot the instance also ASG cannot replace the instance.
Once the reboot is performed we can add back the instance to the ASG.
Before removing the instance make sure to check the minimum value of ASG as there should be always a min number of instances available on ASG.
Also make sure while detaching the instance donot tick the create replace instance as new instances will be created to balance the infra.

# Stand-by method
Rebooting can be done via setting the instance as standby instance.
Now the instance is part of ASG group but will not be replaced by ASG in case of stopping the instance.
While the ASG is deleted these instances will also be deleted
