> **AWS Identity and Access Management (IAM)**: is a service that helps securely manage identities and access to AWS services and resources.


- **IAM Users:**
	- By default all access denied, need to provide access explicitly in a policy.
- **IAM Groups**:
	- Easier to manage permissions by assigning policy to groups - users in the group inherit the group policy.
- **IAM Roles**:
	- Best for use-cases where users need temporary access to resources. When a user assumes a role, they give up their own set of privileges temporarily.
	- Create a role >> Create policy granting permissions for resources >> Assign policy to the role >> Allow relevant users to assume the role.