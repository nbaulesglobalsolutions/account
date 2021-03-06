---

copyright:

  years: 2017, 2018
lastupdated: "2018-08-02"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}

# 카탈로그에 대한 액세스 관리
{: #find-access}

계정 소유자는 계정의 사용자가 계정에 작성된 계정 카탈로그 또는 퍼블릭 서비스에 추가된 개인 서비스의 가시성을 제어할 수 있도록 IAM 정책을 사용하여 액세스를 지정할 수 있습니다. 기본적으로 계정 소유자만 이러한 태스크를 완료할 수 있습니다.

## 계정 소유자로서 액세스를 어떻게 위임합니까?
{: #get-access}

계정 소유자는 액세스 정책을 지정하여 ID 및 액세스 UI를 통해 계정의 사용자에게 액세스를 제공할 수 있습니다. 사용자에게 필수 액세스 권한이 있는지 확인하려면 액세스 정책에 대한 **글로벌 카탈로그** 리소스 및 **관리자** 역할을 선택하십시오.

`viewer` 및 `editor` IAM(Identity and Access Management) 역할을 사용하여 계정의 사용자에게 다른 권한을 부여할 수 있습니다. 각 IAM 역할이 계정의 카탈로그에 대한 작업의 컨텍스트 내에서 사용자가 수행할 수 있도록 허용하는 작업에 대해 자세히 보려면 다음 표를 검토하십시오.

|플랫폼 관리 역할 |조치에 대한 설명 |
|:-----------------|:-----------------|
|뷰어 |계정이 포함되어 있지 않은 경우에도 개인 서비스를 볼 수 있지만 변경할 수는 없습니다. |
|편집자 |오브젝트 메타데이터를 변경할 수 있지만 가시성을 변경할 수는 없습니다. |
|관리자 |오브젝트 메타데이터 또는 가시성을 변경할 수 있습니다.  |
{: caption="표 1. 카탈로그 서비스에 대한 플랫폼 관리 역할 및 조치 예" caption-side="top"}

계정의 사용자에게 액세스를 지정하는 데 대한 단계별 지시사항을 보려면 [리소스에 대한 액세스](/docs/iam/mngiam.html#iammanidaccser#resourceaccess) 문서로 이동하십시오.

## 액세스 권한이 있는지 여부를 어떻게 확인합니까?

다른 사용자의 계정에 추가되는 경우 계정에 추가된 개인용 리소스를 볼 수 있도록 특정 레벨의 액세스를 위임받을 수 있습니다. 또한 계정 소유자에게 계정 카탈로그의 공용 리소스를 볼 수 있는 사용자를 관리하는 기능을 위임받을 수도 있습니다. 기본적으로 이 액세스 권한은 없습니다. 계정 소유자는 이러한 계정 리소스 관리 태스크를 완료하기 위한 액세스 권한을 가질 수 있는 IAM 역할을 사용자에게 부여해야 합니다.

CLI 또는 ID 및 액세스 UI를 사용하여 특정 사용자가 계정에 추가된 개인용 리소스를 볼 수 있도록 하는 액세스 권한이 있는지 여부를 판별할 수 있습니다.

ID 및 액세스 UI 를 사용하려면 다음 단계를 완료하십시오.

1. **관리** > **보안** > **ID 및 액세스**로 이동한 다음 **사용자**를 클릭하십시오.
2. 사용자 목록에서 이름을 클릭하십시오.
3. **액세스 정책** 섹션에서 지정된 액세스 정책을 볼 수 있습니다. 카탈로그에서 개인용 리소스를 보기 위한 계정이 포함된 목록을 업데이트하려면 계정의 카탈로그 리소스에 대한 Cloud IAM 관리자 역할이 있어야 합니다.

[ibmcloud CLI](/docs/cli/reference/ibmcloud/bx_cli.html#ibmcloud_commands_iam)를 사용하려면 다음 단계를 완료하십시오.

사용자 이름과 함께 명령 `ibmcloud iam user-policies <your-username>`을 입력하여 자신이 CLI에서 선택한 계정의 관리자인지 확인하십시오. 계정의 관리자가 아닌 경우 이러한 명령은 권한이 부여되지 않았다는 오류를 리턴합니다.
{: tip}
