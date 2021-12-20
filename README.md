<!-- start title -->

# GitHub Action:Branch Protection Bot

<!-- end title -->
<!-- start description -->

An action to modify branch protection settings

<!-- end description -->
<!-- start contents -->
<!-- end contents -->
<!-- start usage -->

```yaml
- uses: Unsupervisedcom/action-branch-protection-bot@undefined
  with:
    # Github token to use
    token: ""

    # Boolean, if true the action will set `include admins` on the branch protection
    # rule
    # Default: true
    set-include-admins: ""

    # Boolean, if true the action will set `include admins` to true on the branch
    # protection rule, else it will set `include admins` to false
    # Default: false
    include-admins: ""

    # Repo owner
    # Default: ${{ github.repository_owner }}
    owner: ""

    # Github repo name
    # Default: ${{ github.event.repository.name }}
    repo: ""

    # Branch change branch protection rules for
    # Default: ${{ github.ref }}
    branch: ""
```

<!-- end usage -->
   <!-- start inputs -->

| **Input**                | **Description**                                                                                                                         |              **Default**              | **Required** |
| :----------------------- | :-------------------------------------------------------------------------------------------------------------------------------------- | :-----------------------------------: | :----------: |
| **`token`**              | Github token to use                                                                                                                     |                                       |   **true**   |
| **`set-include-admins`** | Boolean, if true the action will set `include admins` on the branch protection rule                                                     |                `true`                 |  **false**   |
| **`include-admins`**     | Boolean, if true the action will set `include admins` to true on the branch protection rule, else it will set `include admins` to false |                                       |  **false**   |
| **`owner`**              | Repo owner                                                                                                                              |   `${{ github.repository_owner }}`    |  **false**   |
| **`repo`**               | Github repo name                                                                                                                        | `${{ github.event.repository.name }}` |  **false**   |
| **`branch`**             | Branch change branch protection rules for                                                                                               |          `${{ github.ref }}`          |  **false**   |

<!-- end inputs -->
   <!-- start outputs -->

| **Output** | **Description**         | **Default** | **Required** |
| :--------- | :---------------------- | ----------- | ------------ |
| `time`     | The time we greeted you |             |              |

<!-- end outputs -->
   <!-- start examples -->

### Example usage

```yaml
on: [push]

jobs:
  hello_world_job:
    runs-on: ubuntu-latest
    name: A job to say hello
    steps:
      - name: Hello world action step
        id: hello
        uses: Unsupervisedcom/action-branch-protection-bot@v1
        with:
          who-to-greet: "Mona the Octocat"
      # Use the output from the `hello` step
      - name: Get the output time
        run: echo "The time was ${{ steps.hello.outputs.time }}"
```

<!-- end examples -->
<!-- start [.github/ghdocs/examples/] -->
<!-- end [.github/ghdocs/examples/] -->
