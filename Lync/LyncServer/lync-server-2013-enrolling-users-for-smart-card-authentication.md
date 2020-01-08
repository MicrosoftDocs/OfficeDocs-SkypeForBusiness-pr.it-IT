---
title: "Lync Server 2013: registrazione degli utenti per l'autenticazione tramite smart card"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enrolling users for smart card authentication
ms:assetid: a6445a83-a94b-423f-ba2a-12b5f84c5d75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308570(v=OCS.15)
ms:contentKeyID: 54973691
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11e74f35119a083aacd8440aec53594b8091b8e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980643"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enrolling-users-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="821d2-102">Registrazione degli utenti per l'autenticazione tramite smart card in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="821d2-102">Enrolling users for smart card authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="821d2-103">_**Argomento Ultima modifica:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="821d2-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="821d2-104">Sono in genere disponibili due metodi per l'iscrizione degli utenti per l'autenticazione tramite smart card.</span><span class="sxs-lookup"><span data-stu-id="821d2-104">There are generally two methods for enrolling users for smart card authentication.</span></span> <span data-ttu-id="821d2-105">Il metodo più semplice consiste nel fatto che gli utenti si iscrivono direttamente per l'autenticazione con smart card usando la registrazione Web, mentre il metodo più complesso prevede l'uso di un agente di registrazione.</span><span class="sxs-lookup"><span data-stu-id="821d2-105">The easier method involves having users enroll directly for smart card authentication using web enrollment, while the more complex method involves using an enrollment agent.</span></span> <span data-ttu-id="821d2-106">Questo argomento riguarda l'autoregistrazione per i certificati smartcard.</span><span class="sxs-lookup"><span data-stu-id="821d2-106">This topic focuses on self-enrollment for smartcard certificates.</span></span>

<span data-ttu-id="821d2-107">Per altre informazioni sull'iscrizione per conto degli utenti come agente di registrazione, vedere registrare i certificati per conto di altri utenti [http://go.microsoft.com/fwlink/p/?LinkID=313367](http://go.microsoft.com/fwlink/p/?linkid=313367).</span><span class="sxs-lookup"><span data-stu-id="821d2-107">For more information on enrolling on behalf of users as an enrollment agent, see Enroll for Certificates on Behalf of Other Users at [http://go.microsoft.com/fwlink/p/?LinkID=313367](http://go.microsoft.com/fwlink/p/?linkid=313367).</span></span>

<div>

## <a name="to-enroll-users-for-smart-card-authentication"></a><span data-ttu-id="821d2-108">Per registrare gli utenti per l'autenticazione tramite smart card</span><span class="sxs-lookup"><span data-stu-id="821d2-108">To Enroll Users for Smart Card Authentication</span></span>

1.  <span data-ttu-id="821d2-109">Accedere alla workstation Windows 8 usando le credenziali di un utente abilitato per Lync.</span><span class="sxs-lookup"><span data-stu-id="821d2-109">Log in to the Windows 8 workstation using the credentials of a Lync-enabled user.</span></span>

2.  <span data-ttu-id="821d2-110">Avviare Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="821d2-110">Launch Internet Explorer.</span></span>

3.  <span data-ttu-id="821d2-111">Passare alla pagina di **registrazione Web Authority Certificate** (ad esempio https://MyCA.contoso.com/certsrv).</span><span class="sxs-lookup"><span data-stu-id="821d2-111">Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="821d2-112">Se si usa Internet Explorer 10, potrebbe essere necessario visualizzare il sito Web in modalità compatibilità.</span><span class="sxs-lookup"><span data-stu-id="821d2-112">If you are using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

    
    </div>

4.  <span data-ttu-id="821d2-113">Nella pagina di **benvenuto** selezionare **Richiedi un certificato**.</span><span class="sxs-lookup"><span data-stu-id="821d2-113">On the **Welcome** Page, select **Request a certificate**.</span></span>

5.  <span data-ttu-id="821d2-114">Selezionare quindi **Advanced request**.</span><span class="sxs-lookup"><span data-stu-id="821d2-114">Next, select **Advanced Request**.</span></span>

6.  <span data-ttu-id="821d2-115">Selezionare **Crea e invia una richiesta a questa CA**.</span><span class="sxs-lookup"><span data-stu-id="821d2-115">Select **Create and submit a request to this CA**.</span></span>

7.  <span data-ttu-id="821d2-116">Selezionare **utente smartcard** nella sezione **modello di certificato** e completare la richiesta di certificato avanzato con i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="821d2-116">Select **Smartcard User** under the **Certificate Template** section and complete the advanced certificate request with the following values:</span></span>
    
      - <span data-ttu-id="821d2-117">Le **Opzioni principali** confermano le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="821d2-117">**Key Options** confirm he following settings:</span></span>
        
          - <span data-ttu-id="821d2-118">Selezionare il pulsante di opzione **Crea nuovo set di tasti**</span><span class="sxs-lookup"><span data-stu-id="821d2-118">Select the **Create new key set** radio button</span></span>
        
          - <span data-ttu-id="821d2-119">Per **CSP**selezionare **provider di crittografia Smart Card Microsoft base**</span><span class="sxs-lookup"><span data-stu-id="821d2-119">For **CSP**, select **Microsoft Base Smart Card Crypto Provider**</span></span>
        
          - <span data-ttu-id="821d2-120">Per l' **utilizzo delle chiavi**, selezionare **Exchange** (questa è l'unica opzione disponibile).</span><span class="sxs-lookup"><span data-stu-id="821d2-120">For **Key Usage**, select **Exchange** (this is the only option available).</span></span>
        
          - <span data-ttu-id="821d2-121">Per le **dimensioni della chiave**, immettere **2048**</span><span class="sxs-lookup"><span data-stu-id="821d2-121">For **Key Size**, enter **2048**</span></span>
        
          - <span data-ttu-id="821d2-122">Verificare che il **nome del contenitore di tasti automatico** sia selezionato</span><span class="sxs-lookup"><span data-stu-id="821d2-122">Confirm that **Automatic key container name** is selected</span></span>
        
          - <span data-ttu-id="821d2-123">Abbandonare le altre caselle deselezionate.</span><span class="sxs-lookup"><span data-stu-id="821d2-123">Leave the other boxes unchecked.</span></span>
    
      - <span data-ttu-id="821d2-124">In **Opzioni aggiuntive** confermare i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="821d2-124">Under **Additional Options** confirm the following values:</span></span>
        
          - <span data-ttu-id="821d2-125">Per il **formato di richiesta** selezionare **CMC**.</span><span class="sxs-lookup"><span data-stu-id="821d2-125">For **Request Format** select **CMC**.</span></span>
        
          - <span data-ttu-id="821d2-126">Per l' **algoritmo hash** selezionare **SHA1**.</span><span class="sxs-lookup"><span data-stu-id="821d2-126">For **Hash Algorithm** select **sha1**.</span></span>
        
          - <span data-ttu-id="821d2-127">Per **nome descrittivo** immettere il **certificato Smardcard**.</span><span class="sxs-lookup"><span data-stu-id="821d2-127">For **Friendly Name** enter **Smardcard Certificate**.</span></span>

8.  <span data-ttu-id="821d2-128">Se si usa un lettore di smartcard fisico, inserire la smart card nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="821d2-128">If you are using a physical smartcard reader, insert the smart card into the device.</span></span>

9.  <span data-ttu-id="821d2-129">Fare clic su **Invia** per inviare la richiesta di certificato.</span><span class="sxs-lookup"><span data-stu-id="821d2-129">Click **Submit** to submit the certificate request.</span></span>

10. <span data-ttu-id="821d2-130">Quando richiesto, immettere il PIN usato per creare la smart card virtuale.</span><span class="sxs-lookup"><span data-stu-id="821d2-130">When prompted, enter the PIN that was used to create the virtual smart card.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="821d2-131">Il valore PIN della smart card virtuale predefinito è "12345678".</span><span class="sxs-lookup"><span data-stu-id="821d2-131">The default virtual smart card PIN value is ‘12345678’.</span></span>

    
    </div>

11. <span data-ttu-id="821d2-132">Dopo aver emesso il certificato, fare clic su **installa questo certificato** per completare il processo di registrazione.</span><span class="sxs-lookup"><span data-stu-id="821d2-132">Once the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="821d2-133">Se la richiesta di certificato non riesce con l'errore "questo Web browser non supporta la generazione di richieste di certificato," Esistono tre modi possibili per risolvere il problema:</span><span class="sxs-lookup"><span data-stu-id="821d2-133">If your certificate request fails with the error “This Web browser does not support the generation of certificate requests,” there are three possible ways to resolve the issue:</span></span> 
    > <OL>
    > <LI>
    > <P><span data-ttu-id="821d2-134">Abilitare la visualizzazione compatibilità in Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="821d2-134">Enable Compatibility View in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="821d2-135">Abilitare l'opzione attiva impostazioni Intranet in Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="821d2-135">Enable the Turn on Intranet settings option in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="821d2-136">Selezionare l'impostazione Reimposta tutte le aree su livello predefinito nella scheda sicurezza del menu opzioni di Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="821d2-136">Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.</span></span></P></LI></OL>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

