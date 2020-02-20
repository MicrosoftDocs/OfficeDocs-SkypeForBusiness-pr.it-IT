---
title: "Lync Server 2013: Configuring Enterprise CA per l'autenticazione con smart card"
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
ms.openlocfilehash: 315d98e26b471e2d9dd84dcb70cd7302e924e9b3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151558"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-ca-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="96e8b-102">Configurazione di CA dell'organizzazione per l'autenticazione con smart card in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96e8b-102">Configuring Enterprise CA for smart card authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96e8b-103">_**Ultimo argomento modificato:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="96e8b-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="96e8b-104">Nella sezione seguente viene descritto come configurare un'autorità di certificazione (CA) radice dell'organizzazione per il supporto dell'autenticazione con smart card.</span><span class="sxs-lookup"><span data-stu-id="96e8b-104">The following section describes how to configure an Enterprise Root Certification Authority (CA) to support smart card authentication.</span></span> <span data-ttu-id="96e8b-105">Per informazioni su come installare una CA radice dell'organizzazione, vedere Install a Enterprise Root Certification Authority [https://go.microsoft.com/fwlink/p/?LinkID=313364](https://go.microsoft.com/fwlink/p/?linkid=313364)at.</span><span class="sxs-lookup"><span data-stu-id="96e8b-105">For information on how to install an Enterprise Root CA, see Install an Enterprise Root Certification Authority at [https://go.microsoft.com/fwlink/p/?LinkID=313364](https://go.microsoft.com/fwlink/p/?linkid=313364).</span></span>

<div>

## <a name="configuring-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a><span data-ttu-id="96e8b-106">Configurazione di un'autorità di certificazione radice dell'organizzazione per il supporto dell'autenticazione con smart card</span><span class="sxs-lookup"><span data-stu-id="96e8b-106">Configuring an Enterprise Root Certificate Authority to Support Smart Card Authentication</span></span>

<span data-ttu-id="96e8b-107">Nella procedura seguente viene descritto come configurare una CA radice dell'organizzazione per il supporto dell'autenticazione con smart card:</span><span class="sxs-lookup"><span data-stu-id="96e8b-107">The following steps describe how to configure an Enterprise Root CA to support Smart Card Authentication:</span></span>

1.  <span data-ttu-id="96e8b-108">Accedere al computer della CA dell'organizzazione utilizzando un account di amministratore di dominio.</span><span class="sxs-lookup"><span data-stu-id="96e8b-108">Log in to the Enterprise CA computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="96e8b-109">Avviare System Manager e verificare che sia installato il ruolo di registrazione Web dell'autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="96e8b-109">Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.</span></span>

3.  <span data-ttu-id="96e8b-110">Dal menu **strumenti di amministrazione** , aprire la console di gestione **autorità di certificazione** .</span><span class="sxs-lookup"><span data-stu-id="96e8b-110">From the **Administrative Tools** menu, open the **Certification Authority** management console.</span></span>

4.  <span data-ttu-id="96e8b-111">Nel riquadro di spostamento espandere **autorità di certificazione**.</span><span class="sxs-lookup"><span data-stu-id="96e8b-111">In the Navigation pane, expand **Certification Authority**.</span></span>

5.  <span data-ttu-id="96e8b-112">Fare clic con il pulsante destro del mouse su **modelli di certificato**, selezionare **nuovo**e quindi selezionare **modello di certificato da emettere**.</span><span class="sxs-lookup"><span data-stu-id="96e8b-112">Right click on **Certificate Templates**, select **New**, then select **Certificate Template to Issue**.</span></span>

6.  <span data-ttu-id="96e8b-113">Selezionare **l'agente di registrazione, l'** **utente smartcard**e l' **accesso smartcard**.</span><span class="sxs-lookup"><span data-stu-id="96e8b-113">Select **Enrollment Agent**, **Smartcard User**, and **Smartcard Logon**.</span></span>

7.  <span data-ttu-id="96e8b-114">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="96e8b-114">Click **OK**.</span></span>

8.  <span data-ttu-id="96e8b-115">Fare clic con il pulsante destro su **modelli di certificato**.</span><span class="sxs-lookup"><span data-stu-id="96e8b-115">Right click on **Certificate Templates**.</span></span>

9.  <span data-ttu-id="96e8b-116">Selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="96e8b-116">Select **Manage**.</span></span>

10. <span data-ttu-id="96e8b-117">Aprire le proprietà del modello utente smartcard.</span><span class="sxs-lookup"><span data-stu-id="96e8b-117">Open the properties of the Smartcard User template.</span></span>

11. <span data-ttu-id="96e8b-118">Fare clic sulla scheda **sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="96e8b-118">Click on the **Security** tab.</span></span>

12. <span data-ttu-id="96e8b-119">Modificare le autorizzazioni come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="96e8b-119">Change the permissions as follows:</span></span>
    
      - <span data-ttu-id="96e8b-120">Aggiungere singoli account di Active Directory con autorizzazioni di lettura/registrazione (Consenti) oppure</span><span class="sxs-lookup"><span data-stu-id="96e8b-120">Add individual user AD accounts with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="96e8b-121">Aggiungere un gruppo di sicurezza contenente gli utenti di smart card con autorizzazioni di lettura/registrazione (Consenti) oppure</span><span class="sxs-lookup"><span data-stu-id="96e8b-121">Add a security group containing smart card users with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="96e8b-122">Aggiungere il gruppo Domain Users con autorizzazioni di lettura/registrazione (Consenti)</span><span class="sxs-lookup"><span data-stu-id="96e8b-122">Add the Domain Users group with Read/Enroll (Allow) permissions</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

