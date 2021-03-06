---

copyright:

  years: 2017, 2018

lastupdated: "2018-08-02"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# 管理 IAM 存取
{: #iammanidaccser}

若要管理存取權，或指派使用者的新存取權，您必須是帳戶擁有者、帳戶中所有服務的管理者，或是針對特定服務或服務實例指派的管理者。如需存取原則及角色的相關資訊，請參閱 [IAM 存取](/docs/iam/users_roles.html)。

## 編輯現有存取權

1. 從功能表列中，按一下**管理** &gt; **安全** &gt; **身分及存取**，然後選取**使用者**。
2. 選取您要指派存取權的使用者名稱。
3. 從您要編輯的原則列中，選取**動作**功能表，然後按一下**編輯原則**。
4. 編輯原則。
5. 按一下**儲存**。

若要使用 CLI 更新使用者原則，您可以使用 [ibmcloud iam user-policy-update](/docs/cli/reference/ibmcloud/cli_api_policy.html#ibmcloud_iam_user_policy_update) 指令。
```
ibmcloud iam user-policy-update USER_NAME POLICY_ID [-v, --version VERSION] {-f, --file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```
{: codeblock}

## 指派新存取權
{: #assignaccess}

若要讓使用者存取所有帳戶資源，以管理使用者存取權、建立資源群組，以及完成所有其他 IAM 管理作業，請針對此原則選取已指派**管理者**角色的**所有已啟用身分及存取的服務**選項。
{: tip}

### 資源群組內的資源存取權 

若要指派資源群組中所有資源的存取權，或只指派資源群組內一項服務的存取權，請完成下列步驟：

1. 從功能表列中，按一下**管理** &gt; **安全** &gt; **身分及存取**，然後選取**使用者**。
2. 從您要指派存取權的使用者列中，選取**動作**功能表，然後按一下**指派存取權**。
3. 選取以**指派資源群組內的存取權**。
4. 選取資源群組。
5. 選擇**指派資源群組存取權**欄位的角色，讓使用者在其儀表板上檢視資源群組、編輯資源群組名稱，或管理使用者對群組的存取權。如果您要使用者只能存取您指定的資源，而非其所屬組織內的群組，則可以選取**不可存取**。
6. 選取資源群組內的服務，或選取以提供所選取群組內所有服務的存取權。
7. 選擇任何角色組合，以指派使用者想要的存取權。此存取權僅適用於您為原則選取的資源。它未提供對本身為資源群組之實際容器的存取權。
8. 按一下**指派**。

### 資源存取權
{: #resourceaccess}

若要指派帳戶中個別資源的存取權，或帳戶中所有資源的存取權，請完成下列步驟： 

1. 從功能表列中，按一下**管理** &gt; **安全** &gt; **身分及存取**，然後選取**使用者**。
2. 從您要指派存取權的使用者列中，選取**動作**功能表，然後按一下**指派存取權**。
3. 選取以**指派對資源的存取權**。
4. 選取服務，或選取**所有已啟用身分及存取的服務**。
5. 當系統提示您時，請選取**所有現行地區**或特定地區。
 
6. 選取**所有現行服務實例**，或選取特定服務實例。
7. 視您選取的服務而定，可能會看到下列欄位。如果您不輸入這些欄位的值，原則會在服務實例層次指派，而非儲存區層次。 
    * **資源類型**：輸入 **bucket**。
    * **資源 ID**：輸入您的儲存區名稱。
8. 選擇任何角色組合，以指派使用者想要的存取權。
9. 按一下**指派**。


## 移除存取權

1. 從功能表列中，按一下**管理** &gt; **安全** &gt; **身分及存取**，然後選取**使用者**。
2. 選取您要移除其存取權的使用者名稱。
3. 從您要移除的原則列中，選取**動作**功能表，然後按一下**移除**。
4. 檢閱您即將移除的使用者原則詳細資料，然後按一下**移除**進行確認。

若要使用 CLI 移除使用者原則，您可以使用 [ibmcloud iam user-policy-delete](/docs/cli/reference/ibmcloud/cli_api_policy.html#ibmcloud_iam_user_policy_delete) 指令。
```
ibmcloud iam user-policy-delete USER_ID POLICY_ID [-f, --force]
```
{: codeblock}

## 檢閱已指派的存取權

如果您需要檢閱您在已加入之帳戶中的獲指派存取權，請完成下列步驟：

1. 從功能表列中，按一下**管理** &gt; **安全** &gt; **身分及存取**，然後選取**使用者**。
2. 選取名稱。
3. 在**存取原則**區段中，檢閱已指派的存取權。

如果您需要其他專用權，則必須與帳戶擁有者聯絡來更新存取權，或是與服務或服務實例的管理者聯絡來更新 Cloud IAM 存取原則。
