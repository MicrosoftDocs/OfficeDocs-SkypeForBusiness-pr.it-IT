---
title: Abilitare gli utenti per VoIP aziendale in locale
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: Per consentire a un utente di utilizzare il sistema telefonico (cloud PBX), è necessario innanzitutto abilitarli per VoIP aziendale e assegnare loro un numero di telefono. A tale scopo, è possibile utilizzare la distribuzione locale mentre l'utente è ancora ospitato nella distribuzione locale.
ms.openlocfilehash: 7fc629114900cb9f4d825bd8fdc8e946e6c63880
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359192"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="77ed4-104">Abilitare gli utenti per VoIP aziendale in locale</span><span class="sxs-lookup"><span data-stu-id="77ed4-104">Enable the users for Enterprise Voice on premises</span></span>
 
<span data-ttu-id="77ed4-105">Per consentire a un utente di utilizzare il sistema telefonico (cloud PBX), è necessario innanzitutto abilitarli per VoIP aziendale e assegnare loro un numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="77ed4-105">For a user to use Phone System (Cloud PBX), you must first enable them for Enterprise Voice and assign them a phone number.</span></span> <span data-ttu-id="77ed4-106">A tale scopo, è possibile utilizzare la distribuzione locale mentre l'utente è ancora ospitato nella distribuzione locale.</span><span class="sxs-lookup"><span data-stu-id="77ed4-106">You do this using your on-premises deployment while the user is still homed in the on-premises deployment.</span></span>

> [!Important]
> <span data-ttu-id="77ed4-107">Skype for business online si ritirerà il 31 luglio 2021 dopo il quale il servizio non sarà più accessibile.</span><span class="sxs-lookup"><span data-stu-id="77ed4-107">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="77ed4-108">Inoltre, la connettività PSTN tra l'ambiente locale e Skype for Business Server o il Cloud Connector Edition e Skype for business online non sarà più supportato.</span><span class="sxs-lookup"><span data-stu-id="77ed4-108">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="77ed4-109">Informazioni su come connettere la rete di telefonia locale ai team che utilizzano il [routing diretto](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="77ed4-109">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a><span data-ttu-id="77ed4-110">Per abilitare un utente per VoIP aziendale in locale e assegnare un numero di telefono</span><span class="sxs-lookup"><span data-stu-id="77ed4-110">To enable a user for Enterprise Voice on premises and assign a phone number</span></span>

1. <span data-ttu-id="77ed4-111">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="77ed4-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="77ed4-112">Usare il menu Start o il collegamento sul desktop per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="77ed4-112">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    <span data-ttu-id="77ed4-113">È inoltre possibile aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="77ed4-113">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="77ed4-114">Sulla barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="77ed4-114">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="77ed4-115">Nella casella **Cerca utenti** digitare anche solo la prima parte del nome visualizzato, del nome, del cognome, del nome dell'account di Gestione account di protezione, dell'indirizzo SIP o dell'URI (Uniform Resource Identifier) di linea dell'account utente da abilitare e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="77ed4-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="77ed4-116">Nella tabella fare clic sull'account utente di Skype for business online che si desidera abilitare per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="77ed4-116">In the table, click the Skype for Business Online user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="77ed4-117">Scegliere **Mostra dettagli**dal menu **modifica** .</span><span class="sxs-lookup"><span data-stu-id="77ed4-117">On the **Edit** menu, click **Show Details**.</span></span>
    
7. <span data-ttu-id="77ed4-118">In **telefonia**, fare clic su **VoIP aziendale**.</span><span class="sxs-lookup"><span data-stu-id="77ed4-118">Under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="77ed4-119">Fare clic su **URI linea**e digitare un numero di telefono normalizzato univoco, ad esempio Tel: + 14255550200.</span><span class="sxs-lookup"><span data-stu-id="77ed4-119">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200).</span></span> <span data-ttu-id="77ed4-120">Quindi fare clic su **commit**.</span><span class="sxs-lookup"><span data-stu-id="77ed4-120">Then click **Commit**.</span></span>
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="77ed4-121">Considerazioni speciali quando si abilitano gli utenti per VoIP aziendale in locale</span><span class="sxs-lookup"><span data-stu-id="77ed4-121">Special considerations when enabling users for Enterprise Voice on premises</span></span>

<span data-ttu-id="77ed4-122">In alcuni casi, potrebbe essere necessario modificare il modo in cui si abilitano gli utenti per VoIP aziendale per assicurarsi che siano in grado di effettuare e ricevere correttamente le chiamate.</span><span class="sxs-lookup"><span data-stu-id="77ed4-122">In some cases, you may need to modify the way you enable users for Enterprise Voice to make sure that they can successfully make and receive calls.</span></span> <span data-ttu-id="77ed4-123">Se nella distribuzione sono presenti utenti che soddisfano le condizioni seguenti, eseguire i passaggi inclusi per abilitare l'utente per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="77ed4-123">If you have users in your deployment that meet the following conditions, perform the steps included to enable the user for Enterprise Voice.</span></span>
  
- <span data-ttu-id="77ed4-124">Se un utente viene creato nell'annuncio locale e quindi è sincronizzato con Skype for business online senza essere abilitato per Skype for business o VoIP aziendale e non dispone di un set di LineURI, eseguire i seguenti cmdlet per ogni utente in questione, sostituendo i valori in \< \> con i valori effettivi dell'ambiente:</span><span class="sxs-lookup"><span data-stu-id="77ed4-124">If a user is created in your on-premises AD and then synchronized with Skype for Business Online without being enabled for Skype for Business or for Enterprise Voice and do not have a LineURI set, run the following cmdlets for each affected user, replacing the values in \< \> with actual values for your environment:</span></span>
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="77ed4-125">Se un utente è già abilitato per Skype for business in locale, ma non è stato abilitato per VoIP aziendale o assegnato a un LineURI prima di essere spostato in Skype for business online, eseguire il seguente cmdlet per ogni utente:</span><span class="sxs-lookup"><span data-stu-id="77ed4-125">If a user is already enabled for Skype for Business on premises, but was not enabled for Enterprise Voice or assigned a LineURI before being moved to Skype for Business Online, run the following cmdlet for each user:</span></span>
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="77ed4-126">Se un utente è già abilitato in Skype for business in locale ma non abilitato per VoIP aziendale, anche se è già stato assegnato un LineURI, eseguire il cmdlet seguente per ogni utente coinvolto:</span><span class="sxs-lookup"><span data-stu-id="77ed4-126">If a user is already enabled in Skype for Business on premises but not enabled for Enterprise Voice, even if already assigned a LineURI, run the following cmdlet for each affected user:</span></span>
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```


