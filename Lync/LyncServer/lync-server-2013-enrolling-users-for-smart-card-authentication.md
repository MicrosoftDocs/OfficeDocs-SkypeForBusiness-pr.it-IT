---
title: "Lync Server 2013: registrazione degli utenti per l'autenticazione con smart card"
description: "Lync Server 2013: registrazione degli utenti per l'autenticazione con smart card."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enrolling users for smart card authentication
ms:assetid: a6445a83-a94b-423f-ba2a-12b5f84c5d75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308570(v=OCS.15)
ms:contentKeyID: 54973691
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d67994d2152ac344934d093a1b6f7d482a7933a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558472"
---
# <a name="enrolling-users-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="e3f7d-103">Registrazione degli utenti per l'autenticazione con smart card in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3f7d-103">Enrolling users for smart card authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3f7d-104">_**Ultimo argomento modificato:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="e3f7d-104">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="e3f7d-105">Sono in genere disponibili due metodi per la registrazione di utenti per l'autenticazione con smart card.</span><span class="sxs-lookup"><span data-stu-id="e3f7d-105">There are generally two methods for enrolling users for smart card authentication.</span></span> <span data-ttu-id="e3f7d-106">Il metodo più semplice consiste nel fatto che gli utenti si iscrivono direttamente per l'autenticazione con smart card tramite la registrazione Web, mentre il metodo più complesso implica l'utilizzo di un agente di registrazione.</span><span class="sxs-lookup"><span data-stu-id="e3f7d-106">The easier method involves having users enroll directly for smart card authentication using web enrollment, while the more complex method involves using an enrollment agent.</span></span> <span data-ttu-id="e3f7d-107">Questo argomento è dedicato alla registrazione automatica dei certificati smartcard.</span><span class="sxs-lookup"><span data-stu-id="e3f7d-107">This topic focuses on self-enrollment for smartcard certificates.</span></span>

<span data-ttu-id="e3f7d-108">Per ulteriori informazioni sull'iscrizione a nome degli utenti come agente di registrazione, vedere registrazione dei certificati per conto di altri utenti all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkID=313367](https://go.microsoft.com/fwlink/p/?linkid=313367) .</span><span class="sxs-lookup"><span data-stu-id="e3f7d-108">For more information on enrolling on behalf of users as an enrollment agent, see Enroll for Certificates on Behalf of Other Users at [https://go.microsoft.com/fwlink/p/?LinkID=313367](https://go.microsoft.com/fwlink/p/?linkid=313367).</span></span>

<div>

## <a name="to-enroll-users-for-smart-card-authentication"></a><span data-ttu-id="e3f7d-109">Per registrare gli utenti per l'autenticazione con smart card</span><span class="sxs-lookup"><span data-stu-id="e3f7d-109">To Enroll Users for Smart Card Authentication</span></span>

1.  <span data-ttu-id="e3f7d-110">Accedere alla workstation Windows 8 utilizzando le credenziali di un utente abilitato per Lync.</span><span class="sxs-lookup"><span data-stu-id="e3f7d-110">Log in to the Windows 8 workstation using the credentials of a Lync-enabled user.</span></span>

2.  <span data-ttu-id="e3f7d-111">Avviare Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="e3f7d-111">Launch Internet Explorer.</span></span>

3.  <span data-ttu-id="e3f7d-112">Passare alla pagina **registrazione Web Authority Certificate** (ad https://MyCA.contoso.com/certsrv) esempio,.</span><span class="sxs-lookup"><span data-stu-id="e3f7d-112">Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e3f7d-113">Se si utilizza Internet Explorer 10, potrebbe essere necessario visualizzare questo sito Web in modalità compatibilità.</span><span class="sxs-lookup"><span data-stu-id="e3f7d-113">If you are using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

    
    </div>

4.  <span data-ttu-id="e3f7d-114">Nella pagina **iniziale** , selezionare **Richiedi un certificato**.</span><span class="sxs-lookup"><span data-stu-id="e3f7d-114">On the **Welcome** Page, select **Request a certificate**.</span></span>

5.  <span data-ttu-id="e3f7d-115">Successivamente, selezionare **richiesta avanzata**.</span><span class="sxs-lookup"><span data-stu-id="e3f7d-115">Next, select **Advanced Request**.</span></span>

6.  <span data-ttu-id="e3f7d-116">Selezionare **Crea e invia una richiesta a questa CA**.</span><span class="sxs-lookup"><span data-stu-id="e3f7d-116">Select **Create and submit a request to this CA**.</span></span>

7.  <span data-ttu-id="e3f7d-117">Selezionare **utente smartcard** nella sezione **modello di certificato** e completare la richiesta di certificato avanzato con i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="e3f7d-117">Select **Smartcard User** under the **Certificate Template** section and complete the advanced certificate request with the following values:</span></span>
    
      - <span data-ttu-id="e3f7d-118">Le **Opzioni principali** confermano le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e3f7d-118">**Key Options** confirm he following settings:</span></span>
        
          - <span data-ttu-id="e3f7d-119">Selezionare il pulsante di opzione **Crea nuovo set di tasti**</span><span class="sxs-lookup"><span data-stu-id="e3f7d-119">Select the **Create new key set** radio button</span></span>
        
          - <span data-ttu-id="e3f7d-120">Per **CSP**, selezionare **Microsoft Base Smart Card Crypto Provider**</span><span class="sxs-lookup"><span data-stu-id="e3f7d-120">For **CSP**, select **Microsoft Base Smart Card Crypto Provider**</span></span>
        
          - <span data-ttu-id="e3f7d-121">Per l' **utilizzo della chiave**, selezionare **Exchange** (è l'unica opzione disponibile).</span><span class="sxs-lookup"><span data-stu-id="e3f7d-121">For **Key Usage**, select **Exchange** (this is the only option available).</span></span>
        
          - <span data-ttu-id="e3f7d-122">Per le **dimensioni della chiave**, immettere **2048**</span><span class="sxs-lookup"><span data-stu-id="e3f7d-122">For **Key Size**, enter **2048**</span></span>
        
          - <span data-ttu-id="e3f7d-123">Confermare che il **nome del contenitore di chiavi automatico** sia selezionato</span><span class="sxs-lookup"><span data-stu-id="e3f7d-123">Confirm that **Automatic key container name** is selected</span></span>
        
          - <span data-ttu-id="e3f7d-124">Lasciare deselezionate le altre caselle.</span><span class="sxs-lookup"><span data-stu-id="e3f7d-124">Leave the other boxes unchecked.</span></span>
    
      - <span data-ttu-id="e3f7d-125">In **Opzioni aggiuntive** confermare i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="e3f7d-125">Under **Additional Options** confirm the following values:</span></span>
        
          - <span data-ttu-id="e3f7d-126">Per il **formato di richiesta** selezionare **CMC**.</span><span class="sxs-lookup"><span data-stu-id="e3f7d-126">For **Request Format** select **CMC**.</span></span>
        
          - <span data-ttu-id="e3f7d-127">Per l' **algoritmo hash** selezionare **SHA1**.</span><span class="sxs-lookup"><span data-stu-id="e3f7d-127">For **Hash Algorithm** select **sha1**.</span></span>
        
          - <span data-ttu-id="e3f7d-128">Per **nome descrittivo** immettere il **certificato Smardcard**.</span><span class="sxs-lookup"><span data-stu-id="e3f7d-128">For **Friendly Name** enter **Smardcard Certificate**.</span></span>

8.  <span data-ttu-id="e3f7d-129">Se si utilizza un lettore di smartcard fisico, inserire la smart card nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e3f7d-129">If you are using a physical smartcard reader, insert the smart card into the device.</span></span>

9.  <span data-ttu-id="e3f7d-130">Fare clic su **Invia** per inviare la richiesta di certificato.</span><span class="sxs-lookup"><span data-stu-id="e3f7d-130">Click **Submit** to submit the certificate request.</span></span>

10. <span data-ttu-id="e3f7d-131">Quando richiesto, immettere il PIN utilizzato per creare la smart card virtuale.</span><span class="sxs-lookup"><span data-stu-id="e3f7d-131">When prompted, enter the PIN that was used to create the virtual smart card.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e3f7d-132">Il valore del PIN della smart card virtuale predefinito è' 12345678'.</span><span class="sxs-lookup"><span data-stu-id="e3f7d-132">The default virtual smart card PIN value is ‘12345678’.</span></span>

    
    </div>

11. <span data-ttu-id="e3f7d-133">Dopo aver emesso il certificato, fare clic su **installa questo certificato** per completare il processo di registrazione.</span><span class="sxs-lookup"><span data-stu-id="e3f7d-133">Once the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e3f7d-134">Se la richiesta di certificato ha esito negativo con l'errore "questo Web browser non supporta la generazione di richieste di certificato", esistono tre modi possibili per risolvere il problema:</span><span class="sxs-lookup"><span data-stu-id="e3f7d-134">If your certificate request fails with the error “This Web browser does not support the generation of certificate requests,” there are three possible ways to resolve the issue:</span></span> 
    > <OL>
    > <LI>
    > <P><span data-ttu-id="e3f7d-135">Abilitare la visualizzazione compatibilità in Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="e3f7d-135">Enable Compatibility View in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="e3f7d-136">Abilitare l'opzione attiva impostazioni Intranet in Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="e3f7d-136">Enable the Turn on Intranet settings option in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="e3f7d-137">Selezionare l'impostazione Reimposta tutte le aree sul livello predefinito nella scheda sicurezza nel menu opzioni di Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="e3f7d-137">Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.</span></span></P></LI></OL>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

