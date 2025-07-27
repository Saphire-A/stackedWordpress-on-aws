1. Key Pair Not Found
`Error Message`:
The key pair 'your-key-name' does not exist

`Cause`:
The EC2 instance required an SSH key pair that was not yet created in the selected AWS region.

Resolution:
Manually created the key pair via the AWS Console and referenced it in the template before launching the stack.

2. Security Group Misconfiguration
`Problem`:
The EC2 instance and WordPress site were not accessible via browser or SSH.

`Cause`:
Missing or incorrect inbound rules in the security group—particularly for HTTP (port 80) and SSH (port 22).

Resolution:
Updated the template to allow necessary inbound traffic on required ports.

3. Stack Rollback Due to Incomplete or Missing Resources
`Problem`:
Stack creation failed and triggered a rollback.

`Cause`:
Some resources were referenced before being properly defined—such as Elastic IP, UserData, or Output values.

`Resolution`:
Gradually added missing dependencies and restructured the template to reflect a complete and valid resource definition.

4. YAML Syntax and Structural Errors
`Cause`:
Improper indentation
Quoting or formatting mistakes
Misplaced parameters or logical blocks

`Resolution`:
Reviewed and corrected YAML structure using consistent indentation, validated the template using AWS tools, and ensured correct alignment of parameters, mappings, and outputs.

5. Multiple Template Revisions
`Observation`:
The template was updated several times to address not only syntax issues but also to include key components that were initially missed—such as AMI references, storage volumes, output mappings, and installation scripts.

`Resolution`:
Iteratively refined the template while gaining a clearer understanding of the full set of resources required for a functional and accessible WordPress deployment.

6. EC2 Running but WordPress Site Not Loading
`Problem`:
The EC2 instance showed as “running” but the WordPress page failed to load in the browser.

`Cause`:
UserData script (Apache and PHP setup) required time to complete

HTTP port (80) was blocked or not open

Web server service might not have started properly

`Resolution`:
Allowed time for EC2 initialization, verified that Apache and PHP were installed and running, and ensured the security group allowed inbound HTTP traffic.