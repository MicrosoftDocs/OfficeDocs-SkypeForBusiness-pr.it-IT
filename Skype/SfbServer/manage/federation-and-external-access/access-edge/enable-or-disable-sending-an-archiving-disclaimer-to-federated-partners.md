---
title: Abilitare o disabilitare l'invio di una dichiarazione di non responsabilità relativa all'archiviazione ai partner federati
ms.reviewer: ''
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: c2f64a617cae938ffe64ec8db313402785413c49
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188861"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a><span data-ttu-id="7ceb9-102">Abilitare o disabilitare l'invio di una dichiarazione di non responsabilità per l'archiviazione a partner federati in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7ceb9-102">Enable or disable sending an Archiving disclaimer to federated partners in Skype for Business Server</span></span>

<span data-ttu-id="7ceb9-103">Al momento della distribuzione degli Edge Server e della federazione abilitata per l'organizzazione, è necessario specificare se inviare automaticamente la dichiarazione di non responsabilità per l'archiviazione a partner federati.</span><span class="sxs-lookup"><span data-stu-id="7ceb9-103">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to automatically send the archiving disclaimer to federated partners.</span></span> <span data-ttu-id="7ceb9-104">Se si archiviano comunicazioni esterne, è necessario abilitare l'invio di una dichiarazione di non responsabilità per l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="7ceb9-104">If you archive external communications, you should enable the sending of an archiving disclaimer.</span></span> <span data-ttu-id="7ceb9-105">Usare la procedura descritta in questo argomento per modificare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="7ceb9-105">Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="7ceb9-106">La procedura seguente presuppone che tu abbia già abilitato la Federazione per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7ceb9-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="7ceb9-107">Per informazioni dettagliate sull'abilitazione della Federazione, vedere [abilitare o disabilitare l'accesso remoto agli utenti](enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="7ceb9-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a><span data-ttu-id="7ceb9-108">Per abilitare o disabilitare l'invio di una dichiarazione di non responsabilità per l'archiviazione a partner federati</span><span class="sxs-lookup"><span data-stu-id="7ceb9-108">To enable or disable sending of an archiving disclaimer to federated partners</span></span>

1.  <span data-ttu-id="7ceb9-109">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="7ceb9-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7ceb9-110">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="7ceb9-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="7ceb9-111">Sulla barra di spostamento sinistra fare clic su **accesso utente esterno**, fare clic su **configurazione bordo di Access**.</span><span class="sxs-lookup"><span data-stu-id="7ceb9-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="7ceb9-112">Nella scheda **configurazione di Access Edge** fare clic su **globale**, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="7ceb9-112">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="7ceb9-113">In **modifica configurazione di Access Edge**, in **abilitare le comunicazioni con gli utenti federati**, selezionare o deselezionare la casella di controllo **Invia Disclaimer per l'archiviazione ai partner federati** per abilitare o disabilitare l'invio automatico dell'archiviazione Disclaimer.</span><span class="sxs-lookup"><span data-stu-id="7ceb9-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>

6.  <span data-ttu-id="7ceb9-114">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="7ceb9-114">Click **Commit**.</span></span>

<span data-ttu-id="7ceb9-115">Per consentire agli utenti federati di collaborare con gli utenti nella distribuzione di Skype for Business Server, è necessario che siano configurati almeno un criterio di accesso esterno per supportare l'accesso degli utenti federati.</span><span class="sxs-lookup"><span data-stu-id="7ceb9-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="7ceb9-116">Per informazioni dettagliate su come controllare l'accesso per specifici domini federati, vedere [configurare il supporto per i domini esterni](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)consentiti.</span><span class="sxs-lookup"><span data-stu-id="7ceb9-116">For details about controlling access for specific federated domains, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7ceb9-117">Abilitazione o disabilitazione della dichiarazione di non responsabilità per l'archiviazione tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7ceb9-117">Enabling or disabling the archiving disclaimer by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="7ceb9-118">L'uso della dichiarazione di non responsabilità per l'archiviazione può essere gestito tramite Windows PowerShell e il cmdlet Set-CsAccessEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="7ceb9-118">The use of the archiving disclaimer can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="7ceb9-119">Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7ceb9-119">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-the-archiving-disclaimer"></a><span data-ttu-id="7ceb9-120">Per abilitare la dichiarazione di non responsabilità per l'archiviazione</span><span class="sxs-lookup"><span data-stu-id="7ceb9-120">To enable the archiving disclaimer</span></span>

  - <span data-ttu-id="7ceb9-121">Per abilitare la dichiarazione di non responsabilità per l'archiviazione, imposta il valore della proprietà **EnableArchivingDisclaimer** su True ($true):</span><span class="sxs-lookup"><span data-stu-id="7ceb9-121">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a><span data-ttu-id="7ceb9-122">Per disabilitare la dichiarazione di non responsabilità per l'archiviazione</span><span class="sxs-lookup"><span data-stu-id="7ceb9-122">To disable the archiving disclaimer</span></span>

  - <span data-ttu-id="7ceb9-123">Per disabilitare la dichiarazione di non responsabilità per l'archiviazione, imposta il valore della proprietà **EnableArchivingDisclaimer** su False ($false):</span><span class="sxs-lookup"><span data-stu-id="7ceb9-123">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False


