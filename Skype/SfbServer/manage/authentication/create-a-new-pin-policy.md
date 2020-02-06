---
title: Creare un nuovo criterio PIN in Skype for Business Server
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
ms.assetid: 8bdf0478-fe9f-4371-93ff-db39381a25db
description: 'Riepilogo: creare un nuovo criterio PIN in Skype for Business Server.'
ms.openlocfilehash: 46464962ea53d81978f0d345d63e380a677b152f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818808"
---
# <a name="create-a-new-pin-policy-in-skype-for-business-server"></a><span data-ttu-id="c8edc-103">Creare un nuovo criterio PIN in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c8edc-103">Create a new PIN policy in Skype for Business Server</span></span>
 
<span data-ttu-id="c8edc-104">**Riepilogo:** Creare un nuovo criterio PIN in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c8edc-104">**Summary:** Create a new PIN policy in Skype for Business Server.</span></span>
  
<span data-ttu-id="c8edc-105">È possibile usare la pagina dei **criteri PIN** per specificare l'autenticazione PIN (Personal Identification Number) per gli utenti che si connettono a Skype for business con telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="c8edc-105">You can use the **PIN Policy** page to provide personal identification number (PIN) authentication to users who are connecting to Skype for Business with IP Phones.</span></span> <span data-ttu-id="c8edc-106">Per usare l'autenticazione PIN, verificare che **l'opzione Abilita autenticazione PIN** sia selezionata nelle impostazioni del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="c8edc-106">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span>
  
<span data-ttu-id="c8edc-107">Seguire questa procedura per creare un criterio PIN a livello di utente o a livello di sito.</span><span class="sxs-lookup"><span data-stu-id="c8edc-107">Follow these steps to create a user-level or a site-level PIN policy.</span></span> 
  
### <a name="to-create-a-user-or-site-pin-policy"></a><span data-ttu-id="c8edc-108">Per creare un criterio PIN per un utente o un sito</span><span class="sxs-lookup"><span data-stu-id="c8edc-108">To create a user or site PIN policy</span></span>

1.  <span data-ttu-id="c8edc-109">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. .</span><span class="sxs-lookup"><span data-stu-id="c8edc-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="c8edc-110">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c8edc-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="c8edc-111">Sulla barra di spostamento sinistra fare clic su **sicurezza** e quindi su **criteri PIN**.</span><span class="sxs-lookup"><span data-stu-id="c8edc-111">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="c8edc-112">Nella pagina **criteri PIN** fare clic su **nuovo**e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8edc-112">On the **PIN Policy** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="c8edc-113">Per creare un criterio a livello di utente, fare clic su **criteri utente**.</span><span class="sxs-lookup"><span data-stu-id="c8edc-113">To create a user-level policy, click **User policy**.</span></span> <span data-ttu-id="c8edc-114">In **nome**digitare un nome che descriva il criterio in **nuovo criterio PIN**.</span><span class="sxs-lookup"><span data-stu-id="c8edc-114">In **New PIN Policy**, in **Name**, type a name that describes the policy.</span></span>
    
   - <span data-ttu-id="c8edc-115">Per creare un criterio a livello di sito, fare clic su **criteri sito**.</span><span class="sxs-lookup"><span data-stu-id="c8edc-115">To create a site-level policy, click **Site policy**.</span></span> <span data-ttu-id="c8edc-116">Nel campo **Seleziona ricerca sito** digitare tutto o parte del nome del sito per cui si vuole creare un criterio.</span><span class="sxs-lookup"><span data-stu-id="c8edc-116">In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy.</span></span> <span data-ttu-id="c8edc-117">Nell'elenco dei siti risultante fare clic sul sito desiderato e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c8edc-117">In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="c8edc-118">Nel campo **Descrizione** Digitare una descrizione del criterio PIN.</span><span class="sxs-lookup"><span data-stu-id="c8edc-118">In the **Description** field, type a description of the PIN policy.</span></span>
    
6. <span data-ttu-id="c8edc-119">Nel campo **lunghezza minima PIN** Digitare o selezionare la lunghezza minima del PIN che si vuole consentire.</span><span class="sxs-lookup"><span data-stu-id="c8edc-119">In the **Minimum PIN length** field, type or select the minimum PIN length that you want to allow.</span></span> <span data-ttu-id="c8edc-120">La lunghezza minima predefinita è di cinque cifre.</span><span class="sxs-lookup"><span data-stu-id="c8edc-120">The default minimum length is five digits.</span></span>
    
7. <span data-ttu-id="c8edc-121">Per poter specificare il numero massimo di tentativi di accesso prima che un utente venga bloccato, selezionare la casella di controllo **specifica tentativi di accesso massimo** .</span><span class="sxs-lookup"><span data-stu-id="c8edc-121">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box.</span></span> <span data-ttu-id="c8edc-122">Se non si seleziona questa opzione, il numero massimo di tentativi consentiti viene determinato automaticamente in base alla lunghezza del PIN.</span><span class="sxs-lookup"><span data-stu-id="c8edc-122">If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length.</span></span> <span data-ttu-id="c8edc-123">Per impostazione predefinita, il numero massimo di tentativi viene determinato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c8edc-123">By default, the maximum number of attempts is automatically determined.</span></span>
    
8. <span data-ttu-id="c8edc-124">Se è stata selezionata la casella di controllo **specifica tentativi di accesso massimo** , in **tentativi di accesso massimo**digitare o selezionare il numero massimo di tentativi di accesso che si desidera consentire.</span><span class="sxs-lookup"><span data-stu-id="c8edc-124">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
9. <span data-ttu-id="c8edc-125">Per impostare i pin in scadenza, selezionare la casella di controllo **Abilita scadenza PIN** .</span><span class="sxs-lookup"><span data-stu-id="c8edc-125">To have PINs expire, select the **Enable PIN expiration** check box.</span></span> <span data-ttu-id="c8edc-126">Se non si seleziona questa opzione, i pin non scadono mai.</span><span class="sxs-lookup"><span data-stu-id="c8edc-126">If you do not select this option, PINs will never expire.</span></span> <span data-ttu-id="c8edc-127">Per impostazione predefinita, i pin non scadono mai.</span><span class="sxs-lookup"><span data-stu-id="c8edc-127">By default, PINs never expire.</span></span>
    
10. <span data-ttu-id="c8edc-128">Se è stata selezionata la casella di controllo **Abilita scadenza PIN** , in **PIN scade dopo (giorni)** digitare o selezionare il numero di giorni dopo il quale i pin scadono.</span><span class="sxs-lookup"><span data-stu-id="c8edc-128">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
11. <span data-ttu-id="c8edc-129">In **conteggio cronologia PIN**Digitare il numero di pin che un utente deve creare prima che l'utente possa riutilizzare un PIN.</span><span class="sxs-lookup"><span data-stu-id="c8edc-129">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN.</span></span> <span data-ttu-id="c8edc-130">Per impostazione predefinita, gli utenti possono riutilizzare i loro PIN.</span><span class="sxs-lookup"><span data-stu-id="c8edc-130">By default, users can reuse their PINs.</span></span>
    
12. <span data-ttu-id="c8edc-131">Per consentire modelli comuni di cifre nei pin, ad esempio "1234" e "8888", selezionare la casella di controllo **Consenti schemi comuni** .</span><span class="sxs-lookup"><span data-stu-id="c8edc-131">To allow common patterns of digits in PINs, such as "1234" and "8888", select the **Allow common patterns** check box.</span></span> <span data-ttu-id="c8edc-132">Se non si seleziona questa opzione, sono consentiti solo modelli complessi di cifre.</span><span class="sxs-lookup"><span data-stu-id="c8edc-132">If you do not select this option, only complex patterns of digits are allowed.</span></span> <span data-ttu-id="c8edc-133">Per impostazione predefinita, sono consentiti solo modelli complessi di cifre.</span><span class="sxs-lookup"><span data-stu-id="c8edc-133">By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c8edc-134">È consigliabile non consentire modelli comuni.</span><span class="sxs-lookup"><span data-stu-id="c8edc-134">We recommend that you do not allow common patterns.</span></span> 
  
13. <span data-ttu-id="c8edc-135">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="c8edc-135">Click **Commit**.</span></span>
    

