---
title: "Lync Server 2013: registrazione degli utenti per l'autenticazione con smart card"
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
ms.openlocfilehash: 635565936712fe542c807ea4d4c65f584e836bdc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137425"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enrolling-users-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="2ba52-102">Registrazione degli utenti per l'autenticazione con smart card in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ba52-102">Enrolling users for smart card authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ba52-103">_**Ultimo argomento modificato:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="2ba52-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="2ba52-104">Sono in genere disponibili due metodi per la registrazione di utenti per l'autenticazione con smart card.</span><span class="sxs-lookup"><span data-stu-id="2ba52-104">There are generally two methods for enrolling users for smart card authentication.</span></span> <span data-ttu-id="2ba52-105">Il metodo più semplice consiste nel fatto che gli utenti si iscrivono direttamente per l'autenticazione con smart card tramite la registrazione Web, mentre il metodo più complesso implica l'utilizzo di un agente di registrazione.</span><span class="sxs-lookup"><span data-stu-id="2ba52-105">The easier method involves having users enroll directly for smart card authentication using web enrollment, while the more complex method involves using an enrollment agent.</span></span> <span data-ttu-id="2ba52-106">Questo argomento è dedicato alla registrazione automatica dei certificati smartcard.</span><span class="sxs-lookup"><span data-stu-id="2ba52-106">This topic focuses on self-enrollment for smartcard certificates.</span></span>

<span data-ttu-id="2ba52-107">Per ulteriori informazioni sull'iscrizione a nome degli utenti come agente di registrazione, vedere registrazione dei certificati per conto di altri utenti all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkID=313367](https://go.microsoft.com/fwlink/p/?linkid=313367).</span><span class="sxs-lookup"><span data-stu-id="2ba52-107">For more information on enrolling on behalf of users as an enrollment agent, see Enroll for Certificates on Behalf of Other Users at [https://go.microsoft.com/fwlink/p/?LinkID=313367](https://go.microsoft.com/fwlink/p/?linkid=313367).</span></span>

<div>

## <a name="to-enroll-users-for-smart-card-authentication"></a><span data-ttu-id="2ba52-108">Per registrare gli utenti per l'autenticazione con smart card</span><span class="sxs-lookup"><span data-stu-id="2ba52-108">To Enroll Users for Smart Card Authentication</span></span>

1.  <span data-ttu-id="2ba52-109">Accedere alla workstation Windows 8 utilizzando le credenziali di un utente abilitato per Lync.</span><span class="sxs-lookup"><span data-stu-id="2ba52-109">Log in to the Windows 8 workstation using the credentials of a Lync-enabled user.</span></span>

2.  <span data-ttu-id="2ba52-110">Avviare Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="2ba52-110">Launch Internet Explorer.</span></span>

3.  <span data-ttu-id="2ba52-111">Passare alla pagina **registrazione Web Authority Certificate** (ad esempio https://MyCA.contoso.com/certsrv),.</span><span class="sxs-lookup"><span data-stu-id="2ba52-111">Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2ba52-112">Se si utilizza Internet Explorer 10, potrebbe essere necessario visualizzare questo sito Web in modalità compatibilità.</span><span class="sxs-lookup"><span data-stu-id="2ba52-112">If you are using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

    
    </div>

4.  <span data-ttu-id="2ba52-113">Nella pagina **iniziale** , selezionare **Richiedi un certificato**.</span><span class="sxs-lookup"><span data-stu-id="2ba52-113">On the **Welcome** Page, select **Request a certificate**.</span></span>

5.  <span data-ttu-id="2ba52-114">Successivamente, selezionare **richiesta avanzata**.</span><span class="sxs-lookup"><span data-stu-id="2ba52-114">Next, select **Advanced Request**.</span></span>

6.  <span data-ttu-id="2ba52-115">Selezionare **Crea e invia una richiesta a questa CA**.</span><span class="sxs-lookup"><span data-stu-id="2ba52-115">Select **Create and submit a request to this CA**.</span></span>

7.  <span data-ttu-id="2ba52-116">Selezionare **utente smartcard** nella sezione **modello di certificato** e completare la richiesta di certificato avanzato con i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="2ba52-116">Select **Smartcard User** under the **Certificate Template** section and complete the advanced certificate request with the following values:</span></span>
    
      - <span data-ttu-id="2ba52-117">Le **Opzioni principali** confermano le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2ba52-117">**Key Options** confirm he following settings:</span></span>
        
          - <span data-ttu-id="2ba52-118">Selezionare il pulsante di opzione **Crea nuovo set di tasti**</span><span class="sxs-lookup"><span data-stu-id="2ba52-118">Select the **Create new key set** radio button</span></span>
        
          - <span data-ttu-id="2ba52-119">Per **CSP**, selezionare **Microsoft Base Smart Card Crypto Provider**</span><span class="sxs-lookup"><span data-stu-id="2ba52-119">For **CSP**, select **Microsoft Base Smart Card Crypto Provider**</span></span>
        
          - <span data-ttu-id="2ba52-120">Per l' **utilizzo della chiave**, selezionare **Exchange** (è l'unica opzione disponibile).</span><span class="sxs-lookup"><span data-stu-id="2ba52-120">For **Key Usage**, select **Exchange** (this is the only option available).</span></span>
        
          - <span data-ttu-id="2ba52-121">Per le **dimensioni della chiave**, immettere **2048**</span><span class="sxs-lookup"><span data-stu-id="2ba52-121">For **Key Size**, enter **2048**</span></span>
        
          - <span data-ttu-id="2ba52-122">Confermare che il **nome del contenitore di chiavi automatico** sia selezionato</span><span class="sxs-lookup"><span data-stu-id="2ba52-122">Confirm that **Automatic key container name** is selected</span></span>
        
          - <span data-ttu-id="2ba52-123">Lasciare deselezionate le altre caselle.</span><span class="sxs-lookup"><span data-stu-id="2ba52-123">Leave the other boxes unchecked.</span></span>
    
      - <span data-ttu-id="2ba52-124">In **Opzioni aggiuntive** confermare i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="2ba52-124">Under **Additional Options** confirm the following values:</span></span>
        
          - <span data-ttu-id="2ba52-125">Per il **formato di richiesta** selezionare **CMC**.</span><span class="sxs-lookup"><span data-stu-id="2ba52-125">For **Request Format** select **CMC**.</span></span>
        
          - <span data-ttu-id="2ba52-126">Per l' **algoritmo hash** selezionare **SHA1**.</span><span class="sxs-lookup"><span data-stu-id="2ba52-126">For **Hash Algorithm** select **sha1**.</span></span>
        
          - <span data-ttu-id="2ba52-127">Per **nome descrittivo** immettere il **certificato Smardcard**.</span><span class="sxs-lookup"><span data-stu-id="2ba52-127">For **Friendly Name** enter **Smardcard Certificate**.</span></span>

8.  <span data-ttu-id="2ba52-128">Se si utilizza un lettore di smartcard fisico, inserire la smart card nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2ba52-128">If you are using a physical smartcard reader, insert the smart card into the device.</span></span>

9.  <span data-ttu-id="2ba52-129">Fare clic su **Invia** per inviare la richiesta di certificato.</span><span class="sxs-lookup"><span data-stu-id="2ba52-129">Click **Submit** to submit the certificate request.</span></span>

10. <span data-ttu-id="2ba52-130">Quando richiesto, immettere il PIN utilizzato per creare la smart card virtuale.</span><span class="sxs-lookup"><span data-stu-id="2ba52-130">When prompted, enter the PIN that was used to create the virtual smart card.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2ba52-131">Il valore del PIN della smart card virtuale predefinito è' 12345678'.</span><span class="sxs-lookup"><span data-stu-id="2ba52-131">The default virtual smart card PIN value is ‘12345678’.</span></span>

    
    </div>

11. <span data-ttu-id="2ba52-132">Dopo aver emesso il certificato, fare clic su **installa questo certificato** per completare il processo di registrazione.</span><span class="sxs-lookup"><span data-stu-id="2ba52-132">Once the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2ba52-133">Se la richiesta di certificato ha esito negativo con l'errore "questo Web browser non supporta la generazione di richieste di certificato", esistono tre modi possibili per risolvere il problema:</span><span class="sxs-lookup"><span data-stu-id="2ba52-133">If your certificate request fails with the error “This Web browser does not support the generation of certificate requests,” there are three possible ways to resolve the issue:</span></span> 
    > <OL>
    > <LI>
    > <P><span data-ttu-id="2ba52-134">Abilitare la visualizzazione compatibilità in Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="2ba52-134">Enable Compatibility View in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="2ba52-135">Abilitare l'opzione attiva impostazioni Intranet in Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="2ba52-135">Enable the Turn on Intranet settings option in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="2ba52-136">Selezionare l'impostazione Reimposta tutte le aree sul livello predefinito nella scheda sicurezza nel menu opzioni di Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="2ba52-136">Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.</span></span></P></LI></OL>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

