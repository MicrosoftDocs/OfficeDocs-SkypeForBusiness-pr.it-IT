---
title: "Lync Server 2013: utilizzo dell'autenticazione a due fattori con client Lync"
description: "Lync Server 2013: utilizzo dell'autenticazione a due fattori con client Lync."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using two-factor authentication with Lync client
ms:assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn338071(v=OCS.15)
ms:contentKeyID: 55115593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbfde1d04d4e641c8fbe4817ffce214df891b565
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547282"
---
# <a name="using-two-factor-authentication-with-lync-client-and-lync-server-2013"></a><span data-ttu-id="3f090-103">Utilizzo dell'autenticazione a due fattori con Lync client e Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f090-103">Using two-factor authentication with Lync client and Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f090-104">_**Ultimo argomento modificato:** 2013-07-11_</span><span class="sxs-lookup"><span data-stu-id="3f090-104">_**Topic Last Modified:** 2013-07-11_</span></span>

<span data-ttu-id="3f090-105">In questo argomento viene descritto come utilizzare l'autenticazione a due fattori con il client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="3f090-105">This topic described how to take advantage of two-factor authentication with Lync 2013 client.</span></span>

<div>

## <a name="sign-in-to-lync-2013-for-the-first-time"></a><span data-ttu-id="3f090-106">Accedere a Lync 2013 per la prima volta</span><span class="sxs-lookup"><span data-stu-id="3f090-106">Sign in to Lync 2013 for the first time</span></span>

<span data-ttu-id="3f090-107">Le informazioni di accesso di Lync vengono in genere configurate automaticamente quando viene installato Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="3f090-107">Your Lync sign-in information is usually configured automatically when Lync 2013 is installed.</span></span> <span data-ttu-id="3f090-108">Tuttavia, la prima volta che si utilizza Lync, potrebbe essere necessario avviare manualmente il client.</span><span class="sxs-lookup"><span data-stu-id="3f090-108">But the first time you use Lync, you might have to manually start the client.</span></span>

<span data-ttu-id="3f090-109">**Per accedere a Lync per la prima volta**</span><span class="sxs-lookup"><span data-stu-id="3f090-109">**To sign in to Lync for the first time**</span></span>

1.  <span data-ttu-id="3f090-110">Accedere alla rete dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3f090-110">Log on to your organization’s network.</span></span>

2.  <span data-ttu-id="3f090-111">Selezionare **Avvia** \> **tutti i programmi** \> **Microsoft Lync \> Lync 2013**.</span><span class="sxs-lookup"><span data-stu-id="3f090-111">Select **Start** \> **All Programs** \> **Microsoft Lync \> Lync 2013**.</span></span>
    
    <span data-ttu-id="3f090-112">Verrà visualizzata la schermata di accesso di Lync.</span><span class="sxs-lookup"><span data-stu-id="3f090-112">You should see the Lync sign-in screen.</span></span>
    
      - <span data-ttu-id="3f090-113">Se la casella indirizzo di accesso è già stata compilata, verificare che l'indirizzo visualizzato sia corretto.</span><span class="sxs-lookup"><span data-stu-id="3f090-113">If the sign-in address box is already filled in, confirm that the address shown is correct.</span></span>
    
      - <span data-ttu-id="3f090-114">Se non è corretto o se la casella è vuota, immettere l'indirizzo di accesso di Lync (in genere corrisponde all'indirizzo di posta elettronica).</span><span class="sxs-lookup"><span data-stu-id="3f090-114">If it’s not correct, or if the box is empty, enter your Lync sign-in address (this is usually the same as your email address).</span></span>
    
      - <span data-ttu-id="3f090-115">Se viene visualizzata una casella password vuota, aggiungere la password.</span><span class="sxs-lookup"><span data-stu-id="3f090-115">If an empty password box is displayed, add your password.</span></span>

3.  <span data-ttu-id="3f090-116">Selezionare **accesso**.</span><span class="sxs-lookup"><span data-stu-id="3f090-116">Select **Sign-in**.</span></span>

</div>

<div>

## <a name="sign-out-of-lync"></a><span data-ttu-id="3f090-117">Disconnessione di Lync</span><span class="sxs-lookup"><span data-stu-id="3f090-117">Sign out of Lync</span></span>

<span data-ttu-id="3f090-118">Al termine dell'utilizzo di Lync, è possibile chiudere la visualizzazione, disconnettersi dalla sessione o uscire dal programma, tutto dal menu file.</span><span class="sxs-lookup"><span data-stu-id="3f090-118">When you’re finished using Lync, you can close the display, sign out of your session, or exit from the program, all from the File menu.</span></span> <span data-ttu-id="3f090-119">Nella tabella seguente vengono illustrate le differenze tra le opzioni.</span><span class="sxs-lookup"><span data-stu-id="3f090-119">The following table explains the differences in the options.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3f090-120">Opzione</span><span class="sxs-lookup"><span data-stu-id="3f090-120">Option</span></span></th>
<th><span data-ttu-id="3f090-121">Funzione</span><span class="sxs-lookup"><span data-stu-id="3f090-121">What it does</span></span></th>
<th><span data-ttu-id="3f090-122">Modalità di esecuzione</span><span class="sxs-lookup"><span data-stu-id="3f090-122">How to perform it</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3f090-123">Chiudere</span><span class="sxs-lookup"><span data-stu-id="3f090-123">Close</span></span></p></td>
<td><p><span data-ttu-id="3f090-124">Chiude la visualizzazione di Lync ma consente di continuare a eseguire la sessione di Lync identificata con l'ID utente.</span><span class="sxs-lookup"><span data-stu-id="3f090-124">Closes your Lync display but lets the Lync session identified with your user ID continue to run.</span></span> <span data-ttu-id="3f090-125">In questo modo è possibile continuare a ricevere notifiche e interagire con altri utenti.</span><span class="sxs-lookup"><span data-stu-id="3f090-125">This is so you can continue to get notifications and interact with others.</span></span></p>
<p><span data-ttu-id="3f090-126">È possibile ottenere la visualizzazione in qualsiasi momento facendo clic sull'icona di Lync sulla barra delle applicazioni o nell'area di notifica nella parte inferiore dello schermo.</span><span class="sxs-lookup"><span data-stu-id="3f090-126">You can get the display back at any time by clicking the Lync icon on the taskbar or the notification area at the bottom of your screen.</span></span></p></td>
<td><p><span data-ttu-id="3f090-127">Nella finestra principale di Lync eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3f090-127">On the Lync main window, do one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="3f090-128">Selezionare il pulsante <strong>Opzioni</strong> , quindi fare <strong>File</strong> clic su &gt; <strong>Chiudi</strong>file.</span><span class="sxs-lookup"><span data-stu-id="3f090-128">Select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Close</strong>.</span></span></p></li>
<li><p><span data-ttu-id="3f090-129">Fare clic sul pulsante <strong>Chiudi</strong> (X) nell'angolo in alto a destra della finestra.</span><span class="sxs-lookup"><span data-stu-id="3f090-129">Click the <strong>Close</strong> button (X) in the upper-right corner of the window.</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f090-130">Disconnessione</span><span class="sxs-lookup"><span data-stu-id="3f090-130">Sign out</span></span></p></td>
<td><p><span data-ttu-id="3f090-131">Termina la sessione di Lync associata all'ID utente, ma Lync continua a essere eseguito in background.</span><span class="sxs-lookup"><span data-stu-id="3f090-131">Ends the Lync session associated with your user ID, but Lync continues to run in the background.</span></span> <span data-ttu-id="3f090-132">Quando si effettua l'accesso, verrà visualizzata la finestra di accesso.</span><span class="sxs-lookup"><span data-stu-id="3f090-132">When you sign out, the sign-in window will appear.</span></span></p>
<div>

> [!TIP]  
> <span data-ttu-id="3f090-133">Selezionare <STRONG>Elimina le informazioni</STRONG> di accesso quando si effettua l'accesso per rimuovere il record dell'ID di accesso e della password dal computer.</span><span class="sxs-lookup"><span data-stu-id="3f090-133">Select <STRONG>Delete my sign-in information</STRONG> when you sign out to remove the record of your logon ID and password from the computer.</span></span> <span data-ttu-id="3f090-134">In questo modo, è possibile facilitare la risoluzione dei problemi di accesso per il supporto alle persone.</span><span class="sxs-lookup"><span data-stu-id="3f090-134">Doing this might make it easier for support people to troubleshoot sign-in issues.</span></span> <span data-ttu-id="3f090-135">È inoltre possibile garantire che le informazioni di accesso siano più sicure rendendo difficile per gli utenti non autorizzati l'accesso con le credenziali.</span><span class="sxs-lookup"><span data-stu-id="3f090-135">It can also help ensure your sign-in information is more secure by making it difficult for unauthorized users to log on with your credentials.</span></span>


</div></td>
<td><p><span data-ttu-id="3f090-136">Nella finestra principale di Lync selezionare il pulsante <strong>Opzioni</strong> , quindi selezionare <strong>File</strong> &gt; <strong>disconnessione</strong>file.</span><span class="sxs-lookup"><span data-stu-id="3f090-136">On the Lync main window, select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Sign Out</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f090-137">Uscita</span><span class="sxs-lookup"><span data-stu-id="3f090-137">Exit</span></span></p></td>
<td><p><span data-ttu-id="3f090-138">Termina la sessione di Lync e arresta Lync nel computer.</span><span class="sxs-lookup"><span data-stu-id="3f090-138">Ends your Lync session and shuts down Lync on your computer.</span></span> <span data-ttu-id="3f090-139">Dopo l'uscita, se si desidera riavviare Lync, selezionare <strong>Avvia</strong> &gt; <strong>tutti i programmi</strong> &gt; <strong>Microsoft Lync</strong> &gt; <strong>Lync 2013</strong>.</span><span class="sxs-lookup"><span data-stu-id="3f090-139">After exiting, if you want to restart Lync, select <strong>Start</strong> &gt; <strong>All Programs</strong> &gt; <strong>Microsoft Lync</strong> &gt; <strong>Lync 2013</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3f090-140">Nella finestra principale di Lync, selezionare il pulsante <strong>Opzioni</strong> , quindi selezionare <strong>File</strong> &gt; <strong>Esci</strong>file.</span><span class="sxs-lookup"><span data-stu-id="3f090-140">On the Lync main window, select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Exit</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sign-in-to-lync-with-a-smart-card"></a><span data-ttu-id="3f090-141">Accedere a Lync con una smart card</span><span class="sxs-lookup"><span data-stu-id="3f090-141">Sign in to Lync with a Smart Card</span></span>

<span data-ttu-id="3f090-142">Alcune organizzazioni ora utilizzano un processo di accesso a più passaggi, denominato autenticazione a due fattori, per aumentare la sicurezza per gli utenti di Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="3f090-142">Some organizations now use a multi-step sign-in process, called two-factor authentication, to increase security for their Lync 2013 users.</span></span> <span data-ttu-id="3f090-143">Se si prevede di utilizzare questa opzione, sarà necessario disporre di una "smart card" per accedere a Lync.</span><span class="sxs-lookup"><span data-stu-id="3f090-143">If you’re expected to use this option, you’ll need a “smart card” to sign in to Lync.</span></span> <span data-ttu-id="3f090-144">Le smart card sono disponibili in due tipi, fisico e virtuale:</span><span class="sxs-lookup"><span data-stu-id="3f090-144">Smart cards come in two varieties, physical and virtual:</span></span>

  - <span data-ttu-id="3f090-145">**Fisica**     Circa le dimensioni di una carta di credito.</span><span class="sxs-lookup"><span data-stu-id="3f090-145">**Physical**   About the size of a credit card.</span></span> <span data-ttu-id="3f090-146">È possibile inserirlo in un lettore di smart card quando si effettua l'accesso.</span><span class="sxs-lookup"><span data-stu-id="3f090-146">You insert it into a smart card reader when you log in.</span></span>

  - <span data-ttu-id="3f090-147">**Virtuale**     Non è un oggetto fisico, ma un identificatore elettronico che viene scritto in un chip speciale sul computer, che in sostanza crea la smart card nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="3f090-147">**Virtual**   Not a physical object, but an electronic identifier that gets written to a special chip on your computer, which in essence builds the smart card into your computer.</span></span> <span data-ttu-id="3f090-148">Disponibile solo per l'utilizzo con i computer Windows 8 che contengono il chip TPM (Trusted Platform Module).</span><span class="sxs-lookup"><span data-stu-id="3f090-148">Available only for use with Windows 8 computers that contain the TPM (Trusted Platform Module) chip.</span></span>

<div>

## <a name="enroll-your-smart-card"></a><span data-ttu-id="3f090-149">Registrare la smart card</span><span class="sxs-lookup"><span data-stu-id="3f090-149">Enroll your smart card</span></span>

<span data-ttu-id="3f090-150">Prima di poter accedere con una smart card, è necessario che la scheda sia "registrazione", ovvero che le credenziali utente debbano essere identificate con la scheda.</span><span class="sxs-lookup"><span data-stu-id="3f090-150">Before you can sign in with a smart card, the card must be “enrolled”—that is, your user credentials have to be identified with the card.</span></span> <span data-ttu-id="3f090-151">Questo è il caso se la scheda è fisica o virtuale.</span><span class="sxs-lookup"><span data-stu-id="3f090-151">This is the case whether the card is physical or virtual.</span></span> <span data-ttu-id="3f090-152">Questo processo potrebbe essere già stato eseguito dall'amministratore di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3f090-152">This process may already been carried out by your Lync Server administrator.</span></span> <span data-ttu-id="3f090-153">Verifica se non si è certi che l'operazione sia stata completata.</span><span class="sxs-lookup"><span data-stu-id="3f090-153">Check with them if you’re not sure whether that has been done.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3f090-154">Poiché ogni smart card virtuale è associata solo al dispositivo in cui è installato, sarà necessario registrare una scheda separata per ogni computer Windows 8 utilizzato.</span><span class="sxs-lookup"><span data-stu-id="3f090-154">Since each virtual smart card is associated only with the device it’s installed on, a separate card will need to be enrolled for each Windows 8 computer you use.</span></span>



</div>

<span data-ttu-id="3f090-155">**Per registrare manualmente la smart card**</span><span class="sxs-lookup"><span data-stu-id="3f090-155">**To manually enroll your smart card**</span></span>

1.  <span data-ttu-id="3f090-156">Eseguire l'accesso al computer in cui verrà eseguito Lync.</span><span class="sxs-lookup"><span data-stu-id="3f090-156">Log on to the computer you’ll be running Lync on.</span></span>

2.  <span data-ttu-id="3f090-157">Tramite Internet Explorer, passare alla pagina di registrazione Web dell'autorità di certificazione dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3f090-157">Using Internet Explorer, browse to your organization’s Certificate Authority Web Enrollment page.</span></span>
    
    <span data-ttu-id="3f090-158">Rivolgersi all'amministratore di Lync Server per l'indirizzo Web di questa risorsa se non è già presente.</span><span class="sxs-lookup"><span data-stu-id="3f090-158">Ask your Lync Server administrator for the web address of this resource if you don’t already have it.</span></span> <span data-ttu-id="3f090-159">L'URL avrà un aspetto analogo al seguente: https://MyCA.\ [YourCompanyName \] . com/certsrv.</span><span class="sxs-lookup"><span data-stu-id="3f090-159">The URL will look something like this: https://MyCA.\[yourcompanyname\].com/certsrv.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3f090-160">Se si utilizza Internet Explorer 10, potrebbe essere necessario visualizzare questo sito Web in modalità compatibilità.</span><span class="sxs-lookup"><span data-stu-id="3f090-160">If you’re using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

    
    </div>

3.  <span data-ttu-id="3f090-161">Quando viene richiesto di accedere alla pagina certificazione, eseguire l'accesso utilizzando l'account di dominio (anziché l'amministratore del computer).</span><span class="sxs-lookup"><span data-stu-id="3f090-161">When you’re prompted to log on to the certification page, log on using your domain account (rather than as administrator of your computer).</span></span>

4.  <span data-ttu-id="3f090-162">Nella pagina di benvenuto del sito Web, selezionare **Richiedi un certificato**.</span><span class="sxs-lookup"><span data-stu-id="3f090-162">On the website Welcome Page, select **Request a certificate**.</span></span>

5.  <span data-ttu-id="3f090-163">Selezionare **richiesta avanzata**.</span><span class="sxs-lookup"><span data-stu-id="3f090-163">Select **Advanced Request**.</span></span>

6.  <span data-ttu-id="3f090-164">Selezionare **Crea e invia una richiesta all'autorità di certificazione**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="3f090-164">Select **Create and submit a request to this CA**, then click **Next**.</span></span>

7.  <span data-ttu-id="3f090-165">Verrà visualizzata una pagina denominata stazione di registrazione smart card.</span><span class="sxs-lookup"><span data-stu-id="3f090-165">Now you’ll see a page called Smart Card Enrollment Station.</span></span> <span data-ttu-id="3f090-166">Approvare la richiesta di installazione del controllo ActiveX e quindi completare il modulo di richiesta Advanced Certificate come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="3f090-166">Approve the request to install the ActiveX control, and then complete the Advanced Certificate Request form as follows:</span></span>
    
    1.  <span data-ttu-id="3f090-167">Selezionare **utente smartcard** nell'elenco a discesa **modello di certificato** .</span><span class="sxs-lookup"><span data-stu-id="3f090-167">Select **Smartcard user** from the **Certificate Template** dropdown list.</span></span>
    
    2.  <span data-ttu-id="3f090-168">Selezionare **Crea nuovo set di chiavi**.</span><span class="sxs-lookup"><span data-stu-id="3f090-168">Select **Create new key set**.</span></span>
    
    3.  <span data-ttu-id="3f090-169">Trovare le informazioni sul produttore nell'etichetta della smart card e selezionarlo nell'elenco a discesa **CSP** .</span><span class="sxs-lookup"><span data-stu-id="3f090-169">Find the manufacturer information on the label of your smart card and select that manufacturer from the **CSP** dropdown list.</span></span>
    
    4.  <span data-ttu-id="3f090-170">Selezionare **CSP** come formato di richiesta, se non è già selezionato.</span><span class="sxs-lookup"><span data-stu-id="3f090-170">Select **CSP** as the Request Format, if it’s not already selected.</span></span>
    
    5.  <span data-ttu-id="3f090-171">Selezionare **SHA1** dall'elenco a discesa dell'algoritmo hash, se non è già selezionato.</span><span class="sxs-lookup"><span data-stu-id="3f090-171">Select **sha1** from the Hash Algorithm dropdown list, if it’s not already selected.</span></span>
    
    6.  <span data-ttu-id="3f090-172">Assegnare un nome al certificato che si desidera riconoscere e fare clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="3f090-172">Give your certificate a name you’ll recognize, and click **Submit**.</span></span>

8.  <span data-ttu-id="3f090-173">A questo punto, inserire la smart card vuota nel lettore di schede collegato alla stazione di registrazione e fare clic su **registra**.</span><span class="sxs-lookup"><span data-stu-id="3f090-173">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>

9.  <span data-ttu-id="3f090-174">Quando richiesto, immettere il proprio PIN (Personal Identification Number) e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3f090-174">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3f090-175">Se la persona del supporto tecnico non ha fornito un PIN speciale da utilizzare per registrare la smart card, utilizzare il valore del PIN della smart card predefinita, che è 12345678.</span><span class="sxs-lookup"><span data-stu-id="3f090-175">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span>

    
    </div>

10. <span data-ttu-id="3f090-176">Selezionare l'opzione per imporre all'utente di modificare il PIN al primo utilizzo della smart card.</span><span class="sxs-lookup"><span data-stu-id="3f090-176">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>

11. <span data-ttu-id="3f090-177">A questo punto, inserire la smart card vuota nel lettore di schede collegato alla stazione di registrazione e fare clic su **registra**.</span><span class="sxs-lookup"><span data-stu-id="3f090-177">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>

12. <span data-ttu-id="3f090-178">Quando richiesto, immettere il proprio PIN (Personal Identification Number) e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3f090-178">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3f090-179">Se la persona del supporto tecnico non ha fornito un PIN speciale da utilizzare per registrare la smart card, utilizzare il valore del PIN della smart card predefinita, che è 12345678.</span><span class="sxs-lookup"><span data-stu-id="3f090-179">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span>

    
    </div>

13. <span data-ttu-id="3f090-180">Selezionare l'opzione per imporre all'utente di modificare il PIN al primo utilizzo della smart card.</span><span class="sxs-lookup"><span data-stu-id="3f090-180">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>

14. <span data-ttu-id="3f090-181">Fare clic su **OK** per confermare che il certificato visualizzato contiene le informazioni su di esso.</span><span class="sxs-lookup"><span data-stu-id="3f090-181">Click **OK** to confirm that the certificate displayed has your information on it.</span></span>

15. <span data-ttu-id="3f090-182">Dopo aver visualizzato l'avviso che il certificato è stato emesso, fare clic su **installa questo certificato** per completare il processo di registrazione.</span><span class="sxs-lookup"><span data-stu-id="3f090-182">Once you see the notice that the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>

</div>

<div>

## <a name="sign-in-to-lync-with-your-smart-card-credentials"></a><span data-ttu-id="3f090-183">Accedere a Lync con le credenziali smart card</span><span class="sxs-lookup"><span data-stu-id="3f090-183">Sign in to Lync with your smart card credentials</span></span>

<span data-ttu-id="3f090-184">Prima di utilizzare la smart card per la prima volta, si consiglia di fare clic su **Elimina le informazioni di accesso** nella pagina di accesso di Lync.</span><span class="sxs-lookup"><span data-stu-id="3f090-184">Before you use your smart card for the first time, it’s recommended that you click **Delete my sign-in info** on the Lync sign-in page.</span></span> <span data-ttu-id="3f090-185">In questo modo vengono cancellate le credenziali di accesso archiviate nel computer e viene eliminata una possibile origine di errore.</span><span class="sxs-lookup"><span data-stu-id="3f090-185">Doing this clears any sign-in credentials stored on your computer, and eliminates a possible source of error.</span></span>

<span data-ttu-id="3f090-186">**Per accedere a Lync con le credenziali smart card**</span><span class="sxs-lookup"><span data-stu-id="3f090-186">**To sign in to Lync with your smart card credentials**</span></span>

1.  <span data-ttu-id="3f090-187">Avviare il client Lync.</span><span class="sxs-lookup"><span data-stu-id="3f090-187">Start the Lync client.</span></span>

2.  <span data-ttu-id="3f090-188">Nella schermata di accesso digitare il nome dell'account utente di accesso nella casella **indirizzo di accesso** e quindi fare clic su **Accedi**.</span><span class="sxs-lookup"><span data-stu-id="3f090-188">On the Sign in screen, type your sign in user account name in the **Sign-in address** box, and then click **Sign In**.</span></span>

3.  <span data-ttu-id="3f090-189">Se si utilizza una smart card virtuale, ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="3f090-189">If you are using a virtual smart card, skip this step.</span></span>
    
    <span data-ttu-id="3f090-190">Se si utilizza una smart card fisica, inserire la smart card nel lettore di smart card e quindi fare clic su **OK** quando la scheda viene rilevata.</span><span class="sxs-lookup"><span data-stu-id="3f090-190">If you are using a physical smart card, insert the smart card into your smart card reader and prompted to do so, and then click **OK** when the card is detected.</span></span>

4.  <span data-ttu-id="3f090-191">Digitare il numero di PIN per la smart card e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3f090-191">Type in the PIN number you for your smart card and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3f090-192">Se non è stato assegnato un numero PIN della smart card dalla persona di supporto, utilizzare il valore predefinito, che è 12345678.</span><span class="sxs-lookup"><span data-stu-id="3f090-192">If you were not assigned a smart card PIN number by your support person, use the default value, which is 12345678.</span></span>

    
    </div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

