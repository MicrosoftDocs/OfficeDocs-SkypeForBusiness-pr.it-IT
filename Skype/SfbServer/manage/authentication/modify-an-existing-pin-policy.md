---
title: Modificare un criterio PIN esistente in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 517caaee-3349-4fa6-8d86-e4da3258a445
description: 'Riepilogo: modificare un criterio PIN esistente in Skype for Business Server.'
ms.openlocfilehash: 91ed45efb96c3eb9c2bb114b5d5b8f25d0e00f93
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818778"
---
# <a name="modify-an-existing-pin-policy-in-skype-for-business-server"></a><span data-ttu-id="46fc5-103">Modificare un criterio PIN esistente in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="46fc5-103">Modify an existing PIN policy in Skype for Business Server</span></span>
 
<span data-ttu-id="46fc5-104">**Riepilogo:** Modificare un criterio PIN esistente in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="46fc5-104">**Summary:** Modify an existing PIN policy in Skype for Business Server.</span></span>
  
<span data-ttu-id="46fc5-105">Puoi usare la scheda **criteri PIN** per specificare l'autenticazione PIN (Personal Identification Number) per gli utenti che si connettono a Skype for business con telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="46fc5-105">You can use the **PIN Policy** tab to provide personal identification number (PIN) authentication to users who are connecting to Skype for Business with IP Phones.</span></span> <span data-ttu-id="46fc5-106">Per usare l'autenticazione PIN, verificare che **l'opzione Abilita autenticazione PIN** sia selezionata nelle impostazioni del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="46fc5-106">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span>
  
<span data-ttu-id="46fc5-107">Seguire questa procedura per modificare un criterio PIN a livello di utente o a livello di sito.</span><span class="sxs-lookup"><span data-stu-id="46fc5-107">Follow these steps to modify a user-level or a site-level PIN policy.</span></span> 
  
### <a name="to-modify-an-existing-pin-policy"></a><span data-ttu-id="46fc5-108">Per modificare un criterio PIN esistente</span><span class="sxs-lookup"><span data-stu-id="46fc5-108">To modify an existing PIN policy</span></span>

1.  <span data-ttu-id="46fc5-109">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. .</span><span class="sxs-lookup"><span data-stu-id="46fc5-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="46fc5-110">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="46fc5-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="46fc5-111">Sulla barra di spostamento sinistra fare clic su **sicurezza** e quindi su **criteri PIN**.</span><span class="sxs-lookup"><span data-stu-id="46fc5-111">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="46fc5-112">Nella pagina **criteri PIN** fare clic su un criterio, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="46fc5-112">On the **PIN Policy** page, click a policy, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="46fc5-113">In **modifica criterio PIN**, in **lunghezza minima PIN**, digitare o selezionare la lunghezza minima del PIN che si vuole consentire.</span><span class="sxs-lookup"><span data-stu-id="46fc5-113">In **Edit PIN Policy**, in **Minimum PIN length**, type or select the minimum PIN length that you want to allow.</span></span> <span data-ttu-id="46fc5-114">La lunghezza minima predefinita è di cinque cifre.</span><span class="sxs-lookup"><span data-stu-id="46fc5-114">The default minimum length is five digits.</span></span>
    
6. <span data-ttu-id="46fc5-115">Per poter specificare il numero massimo di tentativi di accesso prima che un utente venga bloccato, selezionare la casella di controllo **specifica tentativi di accesso massimo** .</span><span class="sxs-lookup"><span data-stu-id="46fc5-115">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box.</span></span> <span data-ttu-id="46fc5-116">Se non si seleziona questa opzione, il numero massimo di tentativi consentiti viene determinato automaticamente in base alla lunghezza del PIN.</span><span class="sxs-lookup"><span data-stu-id="46fc5-116">If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length.</span></span> <span data-ttu-id="46fc5-117">Per impostazione predefinita, il numero massimo di tentativi viene determinato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="46fc5-117">By default, the maximum number of attempts is automatically determined.</span></span>
    
7. <span data-ttu-id="46fc5-118">Se è stata selezionata la casella di controllo **specifica tentativi di accesso massimo** , in **tentativi di accesso massimo**digitare o selezionare il numero massimo di tentativi di accesso che si desidera consentire.</span><span class="sxs-lookup"><span data-stu-id="46fc5-118">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
8. <span data-ttu-id="46fc5-119">Per impostare i pin in scadenza, selezionare la casella di controllo **Abilita scadenza PIN** .</span><span class="sxs-lookup"><span data-stu-id="46fc5-119">To have PINs expire, select the **Enable PIN expiration** check box.</span></span> <span data-ttu-id="46fc5-120">Se non si seleziona questa opzione, i pin non scadono mai.</span><span class="sxs-lookup"><span data-stu-id="46fc5-120">If you do not select this option, PINs will never expire.</span></span> <span data-ttu-id="46fc5-121">Per impostazione predefinita, i pin non scadono mai.</span><span class="sxs-lookup"><span data-stu-id="46fc5-121">By default, PINs never expire.</span></span>
    
9. <span data-ttu-id="46fc5-122">Se è stata selezionata la casella di controllo **Abilita scadenza PIN** , in **PIN scade dopo (giorni)** digitare o selezionare il numero di giorni dopo il quale i pin scadono.</span><span class="sxs-lookup"><span data-stu-id="46fc5-122">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
10. <span data-ttu-id="46fc5-123">In **conteggio cronologia PIN**Digitare il numero di pin che un utente deve creare prima che l'utente possa riutilizzare un PIN.</span><span class="sxs-lookup"><span data-stu-id="46fc5-123">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN.</span></span> <span data-ttu-id="46fc5-124">Per impostazione predefinita, gli utenti possono riutilizzare i loro PIN.</span><span class="sxs-lookup"><span data-stu-id="46fc5-124">By default, users can reuse their PINs.</span></span>
    
11. <span data-ttu-id="46fc5-125">Per consentire modelli comuni di cifre nei pin, ad esempio numeri sequenziali e set ripetitivi di numeri, selezionare la casella di controllo **Consenti schemi comuni** .</span><span class="sxs-lookup"><span data-stu-id="46fc5-125">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box.</span></span> <span data-ttu-id="46fc5-126">Se non si seleziona questa opzione, sono consentiti solo modelli complessi di cifre.</span><span class="sxs-lookup"><span data-stu-id="46fc5-126">If you do not select this option, only complex patterns of digits are allowed.</span></span> <span data-ttu-id="46fc5-127">Per impostazione predefinita, sono consentiti solo modelli complessi di cifre.</span><span class="sxs-lookup"><span data-stu-id="46fc5-127">By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="46fc5-128">È consigliabile non consentire modelli comuni.</span><span class="sxs-lookup"><span data-stu-id="46fc5-128">We recommend that you do not allow common patterns.</span></span> 
  
12. <span data-ttu-id="46fc5-129">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="46fc5-129">Click **Commit**.</span></span>
    

