1. Follow this [guide](https://chocolatey.org/install) to install chocolatey
2. Install Visual Studio 2019 if required
3. Clone [Main Shopify Project](https://dev.azure.com/NanyangPoly/IND_KindCitizen/_git/IND_KindCitizen_Theme) from Visual Studio->Team Explorer
4. Checkout your own branch, e.g. "staging_<role>".
<br/>(1) Open the "Git Changes" window.
<br/>(2) Click any selection listed here to open the selection window. If you are curious, this selection stated here is your current working branch.
<br/>(3) Click on 'Remotes' tab.
<br/>(4) Scroll down and look for the branch you wish to checkout. Right-click on that branch, and select "Checkout". _Once you do this, you will find a local branch (same branch name, but without *origin*) will be created under "Locals" tab. This branch will be your local working branch._
<br/>
![wiki_git_checkout_branch_how.png](/.attachments/wiki_git_checkout_branch_how-8d54f48e-c202-436b-bd13-67f96650e4c7.png)

5. Save the following codes as new file **config.yml** to your project. Get your assigned Theme ID from supervisor.

```
development:
  password: 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
  theme_id: "<your theme id here>"
  store: kindcitizen.myshopify.com
```
Important: Try **NOT** to switch branches. Please stick to your own branch. If you do switch branch, this config.xml may need to be changed when doing theme watch or any deployment. Otherwise, other themes will get affected.

7. Navigate to project directory using Powershell

8. Connect to Shopify Online Editor with the following command.
<br/>_Please ensure **theme_id** in config.xml is **your own theme ID**, before you run this command. Otherwise, other themes will get affected._

`theme watch`

9. Make some changes to the codes in Visual Studio(e.g. edit text in home page)
10. You should be able to see your files changes in Powershell.

![image.png](/.attachments/image-084bb358-c835-4836-9e59-79054d3a2096.png)

11. You should be able to preview your changes from Shopify Online Editor.

![image.png](/.attachments/image-9cf1f26a-94de-45b2-be22-590ad5bc89ee.png)

12. Do a regular commit-push your source codes in your own branch, in order to prevent any loss.
13. To submit your changes for integration:
<br/>(a) Push your source codes in your own branch(e.g. dev_stud1) in Visual Studio->Team Explorer.
<br/>(b) Create a pull request in Azure DevOps portal and submit for review. _Please ignore input for "Reviewers" if you are not able to search the user._

![image.png](/.attachments/image-bf83897c-2492-458b-bb93-5c833e37fcb6.png)

![image.png](/.attachments/image-3b36ca04-da32-4490-b07f-cb31007db9df.png)