---
title: Abilitare o disabilitare l'invio di una dichiarazione di non responsabilità relativa all'archiviazione ai partner federati
ms.reviewer: ''
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: 1f0238e177e74dc1263208f9a6a350158825d825
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817356"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a><span data-ttu-id="f67df-102">Abilitare o disabilitare l'invio di una dichiarazione di non responsabilità per l'archiviazione ai partner federati in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f67df-102">Enable or disable sending an Archiving disclaimer to federated partners in Skype for Business Server</span></span>

<span data-ttu-id="f67df-p101">Al momento della distribuzione dei server perimetrali e dell'abilitazione della federazione per l'organizzazione, dovrebbe essere stato specificato se inviare automaticamente la dichiarazione di non responsabilità relativa all'archiviazione ai partner federati. Se si archiviano le comunicazioni esterne, è consigliabile abilitare l'invio di una dichiarazione di non responsabilità relativa all'archiviazione. Utilizzare la procedura descritta in questo argomento per modificare tale configurazione.</span><span class="sxs-lookup"><span data-stu-id="f67df-p101">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to automatically send the archiving disclaimer to federated partners. If you archive external communications, you should enable the sending of an archiving disclaimer. Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="f67df-106">Nella procedura che segue si presuppone che sia stata già abilitata la federazione per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f67df-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="f67df-107">Per informazioni dettagliate sull'abilitazione della federazione, vedere [Abilitare o disabilitare l'accesso degli utenti remoti.](enable-or-disable-remote-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="f67df-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a><span data-ttu-id="f67df-108">Per abilitare o disabilitare l'invio di una dichiarazione di non responsabilità relativa all'archiviazione ai partner federati</span><span class="sxs-lookup"><span data-stu-id="f67df-108">To enable or disable sending of an archiving disclaimer to federated partners</span></span>

1.  <span data-ttu-id="f67df-109">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="f67df-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f67df-110">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f67df-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f67df-111">Sulla barra di spostamento sinistra fare clic su **Accesso utente esterno** e su **Configurazione Access Edge**.</span><span class="sxs-lookup"><span data-stu-id="f67df-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="f67df-112">Nella scheda **Configurazione Access Edge** fare clic su **Globale**, quindi su **Modifica** e infine su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="f67df-112">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="f67df-113">In **Modifica configurazione Access Edge**, in **Abilita comunicazioni con utenti federati**, selezionare o deselezionare la casella di controllo **Invia dichiarazione di non responsabilità relativa all'archiviazione ai partner federati** per abilitare o disabilitare l'invio automatico della dichiarazione di non responsabilità relativa all'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="f67df-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>

6.  <span data-ttu-id="f67df-114">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="f67df-114">Click **Commit**.</span></span>

<span data-ttu-id="f67df-115">Per consentire agli utenti federati di collaborare con gli utenti nella distribuzione di Skype for Business Server, è inoltre necessario aver configurato almeno un criterio di accesso esterno per supportare l'accesso degli utenti federati.</span><span class="sxs-lookup"><span data-stu-id="f67df-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="f67df-116">Per informazioni dettagliate sul controllo dell'accesso per domini federati specifici, vedere [Configurare il supporto per i domini esterni consentiti.](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)</span><span class="sxs-lookup"><span data-stu-id="f67df-116">For details about controlling access for specific federated domains, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f67df-117">Abilitazione o disabilitazione della dichiarazione di non responsabilità per l'archiviazione tramite Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="f67df-117">Enabling or disabling the archiving disclaimer by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="f67df-118">L'utilizzo della dichiarazione di non responsabilità per l'archiviazione può essere gestito utilizzando Windows PowerShell e il cmdlet Set-CsAccessEdgeConfiguration archiviazione.</span><span class="sxs-lookup"><span data-stu-id="f67df-118">The use of the archiving disclaimer can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="f67df-119">Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f67df-119">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-the-archiving-disclaimer"></a><span data-ttu-id="f67df-120">Per abilitare la dichiarazione di non responsabilità per l'archiviazione</span><span class="sxs-lookup"><span data-stu-id="f67df-120">To enable the archiving disclaimer</span></span>

  - <span data-ttu-id="f67df-121">Per abilitare la dichiarazione di non responsabilità relativa all'archiviazione, impostare il valore della proprietà **EnableArchivingDisclaimer** su True ($True):</span><span class="sxs-lookup"><span data-stu-id="f67df-121">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a><span data-ttu-id="f67df-122">Per disabilitare la dichiarazione di non responsabilità per l'archiviazione</span><span class="sxs-lookup"><span data-stu-id="f67df-122">To disable the archiving disclaimer</span></span>

  - <span data-ttu-id="f67df-123">Per disabilitare la dichiarazione di non responsabilità relativa all'archiviazione, impostare il valore della proprietà **EnableArchivingDisclaimer** su False ($False):</span><span class="sxs-lookup"><span data-stu-id="f67df-123">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False


