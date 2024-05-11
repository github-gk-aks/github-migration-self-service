**Scaling Self-Hosted Runners in GitHub Enterprise Cloud**

Here's a step-by-step guide to scale up and down self-hosted runners based on demand:

1. **Webhook Setup**: Set up webhook events for your repository. You can create automation that adds a new self-hosted runner each time you receive a `workflow_job` webhook event with the `queued` activity, which notifies you that a new job is ready for processing¹.

2. **Runner Registration**: Register your runner using `config.sh` and include the `--ephemeral` parameter. This ensures that GitHub only assigns one job to a runner¹. For example:
    ```
    ./config.sh --url https://github.com/octo-org --token example-token --ephemeral
    ```
3. **Runner Deletion**: Once the job has finished, create automation that removes the runner in response to the `workflow_job` `completed` activity¹.

4. **API Authentication**: Register and delete enterprise self-hosted runners using the API. To authenticate to the API, your autoscaling implementation can use an access token. Your access token will require the `manage_runners:enterprise` scope¹.

5. **Ephemeral Runners**: Implement autoscaling with ephemeral self-hosted runners. This approach allows you to manage your runners as ephemeral systems, providing a clean environment for each job¹.

6. **Log Forwarding**: Ensure runner application log files for ephemeral runners are forwarded to an external log storage solution for troubleshooting and diagnostic purposes¹.

7. **Autoscaling Solutions**: Consider using the `actions-runner-controller` (ARC) project, a Kubernetes-based runner autoscaler, if your team has expert Kubernetes knowledge and experience¹.

Remember, this is a high-level plan and the exact implementation can vary based on your specific setup and requirements. Always refer to the official GitHub documentation for the most accurate and up-to-date information¹.

Source: Conversation with Bing, 5/10/2024
(1) Autoscaling with self-hosted runners - GitHub Docs. https://docs.github.com/en/actions/hosting-your-own-runners/managing-self-hosted-runners/autoscaling-with-self-hosted-runners.
(2) Managing self-hosted runners - GitHub Docs. https://docs.github.com/en/actions/hosting-your-own-runners/managing-self-hosted-runners?platform=windows.
(3) GitHub Actions: Ephemeral self-hosted runners & new webhooks for auto .... https://github.blog/changelog/2021-09-20-github-actions-ephemeral-self-hosted-runners-new-webhooks-for-auto-scaling/.
(4) AKS auto-scaling for GitHub self-hosted runners on Azure. https://github.com/nicklegan/aks-auto-scaling-github-self-hosted-runners.
(5) undefined. https://github.com/octo-org.

