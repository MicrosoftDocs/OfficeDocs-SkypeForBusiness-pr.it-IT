---
title: Consentire agli utenti di VoIP aziendale in locale
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: Per consentire a un utente di usare il sistema telefonico in Office 365 (cloud PBX), è necessario prima di tutto abilitare Enterprise Voice e assegnare loro un numero di telefono. A questo scopo, puoi usare la distribuzione locale mentre l'utente è ancora ospitato nella distribuzione locale.
ms.openlocfilehash: 8bf8720896aa8115cb24d3b632b4ae576f466bcc
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003476"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="8fac4-104">Consentire agli utenti di VoIP aziendale in locale</span><span class="sxs-lookup"><span data-stu-id="8fac4-104">Enable the users for Enterprise Voice on premises</span></span>
 
<span data-ttu-id="8fac4-105">Per consentire a un utente di usare il sistema telefonico in Office 365 (cloud PBX), è necessario prima di tutto abilitare Enterprise Voice e assegnare loro un numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="8fac4-105">For a user to use Phone System in Office 365 (Cloud PBX), you must first enable them for Enterprise Voice and assign them a phone number.</span></span> <span data-ttu-id="8fac4-106">A questo scopo, puoi usare la distribuzione locale mentre l'utente è ancora ospitato nella distribuzione locale.</span><span class="sxs-lookup"><span data-stu-id="8fac4-106">You do this using your on-premises deployment while the user is still homed in the on-premises deployment.</span></span>
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a><span data-ttu-id="8fac4-107">Per consentire a un utente di VoIP aziendale locale e assegnare un numero di telefono</span><span class="sxs-lookup"><span data-stu-id="8fac4-107">To enable a user for Enterprise Voice on premises and assign a phone number</span></span>

1. <span data-ttu-id="8fac4-108">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="8fac4-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="8fac4-109">Usare il menu Start o il collegamento sul desktop per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8fac4-109">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    <span data-ttu-id="8fac4-110">È anche possibile aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8fac4-110">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="8fac4-111">Sulla barra di spostamento sinistra fare clic su **utenti**.</span><span class="sxs-lookup"><span data-stu-id="8fac4-111">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="8fac4-112">Nella casella **Cerca utenti** digitare tutto o la prima parte del nome visualizzato, nome, cognome, nome account di Security Accounts Manager (Sam), indirizzo SIP o URI (Uniform Resource Identifier) linea dell'account utente che si vuole abilitare e quindi fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="8fac4-112">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="8fac4-113">Nella tabella fare clic sull'account utente di Skype for business online che si vuole abilitare per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="8fac4-113">In the table, click the Skype for Business Online user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="8fac4-114">Nel menu **modifica** fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="8fac4-114">On the **Edit** menu, click **Show Details**.</span></span>
    
7. <span data-ttu-id="8fac4-115">In **telefonia**fare clic su **VoIP aziendale**.</span><span class="sxs-lookup"><span data-stu-id="8fac4-115">Under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="8fac4-116">Fare clic su **URI linea**e digitare un numero di telefono normalizzato univoco, ad esempio Tel: + 14255550200.</span><span class="sxs-lookup"><span data-stu-id="8fac4-116">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200).</span></span> <span data-ttu-id="8fac4-117">Quindi fare clic su **commit**.</span><span class="sxs-lookup"><span data-stu-id="8fac4-117">Then click **Commit**.</span></span>
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="8fac4-118">Considerazioni speciali per consentire agli utenti di VoIP aziendale in locale</span><span class="sxs-lookup"><span data-stu-id="8fac4-118">Special considerations when enabling users for Enterprise Voice on premises</span></span>

<span data-ttu-id="8fac4-119">In alcuni casi potrebbe essere necessario modificare il modo in cui gli utenti possono eseguire la chiamata a VoIP aziendale per assicurarsi che possano effettuare e ricevere chiamate.</span><span class="sxs-lookup"><span data-stu-id="8fac4-119">In some cases, you may need to modify the way you enable users for Enterprise Voice to make sure that they can successfully make and receive calls.</span></span> <span data-ttu-id="8fac4-120">Se nella distribuzione sono presenti utenti che soddisfano le condizioni seguenti, eseguire i passaggi inclusi per abilitare l'utente per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="8fac4-120">If you have users in your deployment that meet the following conditions, perform the steps included to enable the user for Enterprise Voice.</span></span>
  
- <span data-ttu-id="8fac4-121">Se un utente viene creato nell'annuncio locale e quindi sincronizzato con Skype for business online senza essere abilitato per Skype for business o per VoIP aziendale e non ha un set di LineUri, eseguire i cmdlet seguenti per ogni utente interessato, sostituendo i valori in \< \> con i valori effettivi per l'ambiente:</span><span class="sxs-lookup"><span data-stu-id="8fac4-121">If a user is created in your on-premises AD and then synchronized with Skype for Business Online without being enabled for Skype for Business or for Enterprise Voice and do not have a LineURI set, run the following cmdlets for each affected user, replacing the values in \< \> with actual values for your environment:</span></span>
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="8fac4-122">Se un utente è già abilitato per Skype for business in locale, ma non è stato abilitato per VoIP aziendale o assegnato un LineURI prima di essere spostato in Skype for business online, eseguire il cmdlet seguente per ogni utente:</span><span class="sxs-lookup"><span data-stu-id="8fac4-122">If a user is already enabled for Skype for Business on premises, but was not enabled for Enterprise Voice or assigned a LineURI before being moved to Skype for Business Online, run the following cmdlet for each user:</span></span>
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="8fac4-123">Se un utente è già abilitato in Skype for business in locale ma non abilitato per VoIP aziendale, anche se è già stato assegnato un LineURI, eseguire il cmdlet seguente per ogni utente interessato:</span><span class="sxs-lookup"><span data-stu-id="8fac4-123">If a user is already enabled in Skype for Business on premises but not enabled for Enterprise Voice, even if already assigned a LineURI, run the following cmdlet for each affected user:</span></span>
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```


