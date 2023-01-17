# CloudFormation - Resources Block

---
## Docs and Source
[Source Here](https://docs.aws.amazon.com/cloudformation/index.html)

---
## Explanation and Notes

**[Principal](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_elements_principal.html)**

This property can be set within a resource to indicate who can or cannot have access to something.

So for example, when I created an IAM role for admin endpoints this property can be used for setting specific users/groups that have the ability to set themselves as that IAM role. In our case, as we were unsure of what it will be used for we set it as `*` so that anyone can have that role.

---


#aws 
	#cloudformation
