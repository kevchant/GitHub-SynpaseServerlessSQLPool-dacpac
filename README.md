# GitHub-SynpaseServerlessSQLPool-dacpac

Example of a state-Based deployment that can create a dacpac file based on an existing serverless SQL Pool and deploy it to another Azure Synapse serverless SQL Pool using GitHub Actions. Based on a blog post I wrote called ['Deploy a dacpac to a serverless SQL pool using GitHub Actions](https://www.kevinrchant.com/2023/03/09/deploy-a-dacpac-to-a-serverless-sql-pool-using-github-actions/)'.

You can find the YAML file which you can use as a template in the .github/workflows subfolder.

First the workflow extracts the contents of a database in a serverless SQL Pool to a dacpac. It then deploys the contents of the dacpac to a database in the same  serverless SQL Pool.

Please note that you need the below secrets created for this to work
* TargetFile - The name you want the dacpac file to be called. For example serverless.dacpac
* Azure_credentials - Required to create a temporary firewall rule for your agent
* ServerlessDB_Connection_String - Connection string for the destination database in the serverless SQL Pool

Note that you can extend this however you see fit. For example, you can add a variable for a second serverless SQL Pool endpoint which belongs to another workspace.
