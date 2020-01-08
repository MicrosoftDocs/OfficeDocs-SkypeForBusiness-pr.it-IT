---
title: "Lync Server 2013: configurazione della CA aziendale per l'autenticazione tramite smart card"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Enterprise CA for smart card authentication
ms:assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308571(v=OCS.15)
ms:contentKeyID: 54973692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 890a69d1c863702db0a70cfb2ce3d61f6a75eeae
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984177"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-ca-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="76358-102">Configurazione della CA aziendale per l'autenticazione tramite smart card in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76358-102">Configuring Enterprise CA for smart card authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76358-103">_**Argomento Ultima modifica:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="76358-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="76358-104">La sezione seguente descrive come configurare un'autorità di certificazione (CA) aziendale per supportare l'autenticazione tramite smart card.</span><span class="sxs-lookup"><span data-stu-id="76358-104">The following section describes how to configure an Enterprise Root Certification Authority (CA) to support smart card authentication.</span></span> <span data-ttu-id="76358-105">Per informazioni su come installare una CA radice aziendale, vedere installare un'autorità di [http://go.microsoft.com/fwlink/p/?LinkID=313364](http://go.microsoft.com/fwlink/p/?linkid=313364)certificazione radice aziendale.</span><span class="sxs-lookup"><span data-stu-id="76358-105">For information on how to install an Enterprise Root CA, see Install an Enterprise Root Certification Authority at [http://go.microsoft.com/fwlink/p/?LinkID=313364](http://go.microsoft.com/fwlink/p/?linkid=313364).</span></span>

<div>

## <a name="configuring-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a><span data-ttu-id="76358-106">Configurazione di un'autorità di certificazione radice aziendale per supportare l'autenticazione tramite smart card</span><span class="sxs-lookup"><span data-stu-id="76358-106">Configuring an Enterprise Root Certificate Authority to Support Smart Card Authentication</span></span>

<span data-ttu-id="76358-107">La procedura seguente descrive come configurare una CA radice aziendale per supportare l'autenticazione tramite smart card:</span><span class="sxs-lookup"><span data-stu-id="76358-107">The following steps describe how to configure an Enterprise Root CA to support Smart Card Authentication:</span></span>

1.  <span data-ttu-id="76358-108">Accedere al computer della CA aziendale usando un account di amministratore di dominio.</span><span class="sxs-lookup"><span data-stu-id="76358-108">Log in to the Enterprise CA computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="76358-109">Avviare System Manager e verificare che sia installato il ruolo di registrazione Web Authority Certificate.</span><span class="sxs-lookup"><span data-stu-id="76358-109">Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.</span></span>

3.  <span data-ttu-id="76358-110">Nel menu **strumenti di amministrazione** aprire la console di gestione **autorità di certificazione** .</span><span class="sxs-lookup"><span data-stu-id="76358-110">From the **Administrative Tools** menu, open the **Certification Authority** management console.</span></span>

4.  <span data-ttu-id="76358-111">Nel riquadro di spostamento espandere **autorità di certificazione**.</span><span class="sxs-lookup"><span data-stu-id="76358-111">In the Navigation pane, expand **Certification Authority**.</span></span>

5.  <span data-ttu-id="76358-112">Fare clic con il pulsante destro del mouse sui **modelli di certificato**, scegliere **nuovo**e quindi **modello certificato da emettere**.</span><span class="sxs-lookup"><span data-stu-id="76358-112">Right click on **Certificate Templates**, select **New**, then select **Certificate Template to Issue**.</span></span>

6.  <span data-ttu-id="76358-113">Selezionare **agente di registrazione**, **utente smartcard**e accesso tramite **smartcard**.</span><span class="sxs-lookup"><span data-stu-id="76358-113">Select **Enrollment Agent**, **Smartcard User**, and **Smartcard Logon**.</span></span>

7.  <span data-ttu-id="76358-114">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="76358-114">Click **OK**.</span></span>

8.  <span data-ttu-id="76358-115">Fare clic con il pulsante destro sul **modello di certificato**.</span><span class="sxs-lookup"><span data-stu-id="76358-115">Right click on **Certificate Templates**.</span></span>

9.  <span data-ttu-id="76358-116">Selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="76358-116">Select **Manage**.</span></span>

10. <span data-ttu-id="76358-117">Aprire le proprietà del modello utente smartcard.</span><span class="sxs-lookup"><span data-stu-id="76358-117">Open the properties of the Smartcard User template.</span></span>

11. <span data-ttu-id="76358-118">Fare clic sulla scheda **sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="76358-118">Click on the **Security** tab.</span></span>

12. <span data-ttu-id="76358-119">Modificare le autorizzazioni nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="76358-119">Change the permissions as follows:</span></span>
    
      - <span data-ttu-id="76358-120">Aggiungere singoli account di annunci utente con autorizzazioni di lettura/registrazione (Consenti) oppure</span><span class="sxs-lookup"><span data-stu-id="76358-120">Add individual user AD accounts with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="76358-121">Aggiungere un gruppo di sicurezza contenente gli utenti di smart card con autorizzazioni di lettura/registrazione (Consenti) oppure</span><span class="sxs-lookup"><span data-stu-id="76358-121">Add a security group containing smart card users with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="76358-122">Aggiungere il gruppo Domain Users con le autorizzazioni di lettura/registrazione (Consenti)</span><span class="sxs-lookup"><span data-stu-id="76358-122">Add the Domain Users group with Read/Enroll (Allow) permissions</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

