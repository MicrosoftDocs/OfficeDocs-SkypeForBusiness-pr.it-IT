---
title: "Lync Server 2013: Configuring Enterprise CA per l'autenticazione con smart card"
description: "Lync Server 2013: Configuring Enterprise CA per l'autenticazione con smart card."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Enterprise CA for smart card authentication
ms:assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308571(v=OCS.15)
ms:contentKeyID: 54973692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98044c96dd04d02fd87609918f309cf65227b133
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548442"
---
# <a name="configuring-enterprise-ca-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="fd433-103">Configurazione di CA dell'organizzazione per l'autenticazione con smart card in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd433-103">Configuring Enterprise CA for smart card authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd433-104">_**Ultimo argomento modificato:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="fd433-104">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="fd433-105">Nella sezione seguente viene descritto come configurare un'autorità di certificazione (CA) radice dell'organizzazione per il supporto dell'autenticazione con smart card.</span><span class="sxs-lookup"><span data-stu-id="fd433-105">The following section describes how to configure an Enterprise Root Certification Authority (CA) to support smart card authentication.</span></span> <span data-ttu-id="fd433-106">Per informazioni su come installare una CA radice dell'organizzazione, vedere Install a Enterprise Root Certification Authority at [https://go.microsoft.com/fwlink/p/?LinkID=313364](https://go.microsoft.com/fwlink/p/?linkid=313364) .</span><span class="sxs-lookup"><span data-stu-id="fd433-106">For information on how to install an Enterprise Root CA, see Install an Enterprise Root Certification Authority at [https://go.microsoft.com/fwlink/p/?LinkID=313364](https://go.microsoft.com/fwlink/p/?linkid=313364).</span></span>

<div>

## <a name="configuring-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a><span data-ttu-id="fd433-107">Configurazione di un'autorità di certificazione radice dell'organizzazione per il supporto dell'autenticazione con smart card</span><span class="sxs-lookup"><span data-stu-id="fd433-107">Configuring an Enterprise Root Certificate Authority to Support Smart Card Authentication</span></span>

<span data-ttu-id="fd433-108">Nella procedura seguente viene descritto come configurare una CA radice dell'organizzazione per il supporto dell'autenticazione con smart card:</span><span class="sxs-lookup"><span data-stu-id="fd433-108">The following steps describe how to configure an Enterprise Root CA to support Smart Card Authentication:</span></span>

1.  <span data-ttu-id="fd433-109">Accedere al computer della CA dell'organizzazione utilizzando un account di amministratore di dominio.</span><span class="sxs-lookup"><span data-stu-id="fd433-109">Log in to the Enterprise CA computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="fd433-110">Avviare System Manager e verificare che sia installato il ruolo di registrazione Web dell'autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="fd433-110">Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.</span></span>

3.  <span data-ttu-id="fd433-111">Dal menu **strumenti di amministrazione** , aprire la console di gestione **autorità di certificazione** .</span><span class="sxs-lookup"><span data-stu-id="fd433-111">From the **Administrative Tools** menu, open the **Certification Authority** management console.</span></span>

4.  <span data-ttu-id="fd433-112">Nel riquadro di spostamento espandere **autorità di certificazione**.</span><span class="sxs-lookup"><span data-stu-id="fd433-112">In the Navigation pane, expand **Certification Authority**.</span></span>

5.  <span data-ttu-id="fd433-113">Fare clic con il pulsante destro del mouse su **modelli di certificato**, selezionare **nuovo**e quindi selezionare **modello di certificato da emettere**.</span><span class="sxs-lookup"><span data-stu-id="fd433-113">Right click on **Certificate Templates**, select **New**, then select **Certificate Template to Issue**.</span></span>

6.  <span data-ttu-id="fd433-114">Selezionare **l'agente di registrazione, l'** **utente smartcard**e l' **accesso smartcard**.</span><span class="sxs-lookup"><span data-stu-id="fd433-114">Select **Enrollment Agent**, **Smartcard User**, and **Smartcard Logon**.</span></span>

7.  <span data-ttu-id="fd433-115">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="fd433-115">Click **OK**.</span></span>

8.  <span data-ttu-id="fd433-116">Fare clic con il pulsante destro su **modelli di certificato**.</span><span class="sxs-lookup"><span data-stu-id="fd433-116">Right click on **Certificate Templates**.</span></span>

9.  <span data-ttu-id="fd433-117">Selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="fd433-117">Select **Manage**.</span></span>

10. <span data-ttu-id="fd433-118">Aprire le proprietà del modello utente smartcard.</span><span class="sxs-lookup"><span data-stu-id="fd433-118">Open the properties of the Smartcard User template.</span></span>

11. <span data-ttu-id="fd433-119">Fare clic sulla scheda **sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="fd433-119">Click on the **Security** tab.</span></span>

12. <span data-ttu-id="fd433-120">Modificare le autorizzazioni come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="fd433-120">Change the permissions as follows:</span></span>
    
      - <span data-ttu-id="fd433-121">Aggiungere singoli account di Active Directory con autorizzazioni di lettura/registrazione (Consenti) oppure</span><span class="sxs-lookup"><span data-stu-id="fd433-121">Add individual user AD accounts with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="fd433-122">Aggiungere un gruppo di sicurezza contenente gli utenti di smart card con autorizzazioni di lettura/registrazione (Consenti) oppure</span><span class="sxs-lookup"><span data-stu-id="fd433-122">Add a security group containing smart card users with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="fd433-123">Aggiungere il gruppo Domain Users con autorizzazioni di lettura/registrazione (Consenti)</span><span class="sxs-lookup"><span data-stu-id="fd433-123">Add the Domain Users group with Read/Enroll (Allow) permissions</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

