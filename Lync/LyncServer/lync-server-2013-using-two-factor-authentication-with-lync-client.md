---
title: "Lync Server 2013: utilizzo dell'autenticazione a due fattori con client Lync"
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
ms.openlocfilehash: ebe1e31cd0f8c5ff90ba6fa88530236c83e371bf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42116719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-two-factor-authentication-with-lync-client-and-lync-server-2013"></a><span data-ttu-id="dd2fb-102">Utilizzo dell'autenticazione a due fattori con Lync client e Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd2fb-102">Using two-factor authentication with Lync client and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd2fb-103">_**Ultimo argomento modificato:** 2013-07-11_</span><span class="sxs-lookup"><span data-stu-id="dd2fb-103">_**Topic Last Modified:** 2013-07-11_</span></span>

<span data-ttu-id="dd2fb-104">In questo argomento viene descritto come utilizzare l'autenticazione a due fattori con il client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-104">This topic described how to take advantage of two-factor authentication with Lync 2013 client.</span></span>

<div>

## <a name="sign-in-to-lync-2013-for-the-first-time"></a><span data-ttu-id="dd2fb-105">Accedere a Lync 2013 per la prima volta</span><span class="sxs-lookup"><span data-stu-id="dd2fb-105">Sign in to Lync 2013 for the first time</span></span>

<span data-ttu-id="dd2fb-106">Le informazioni di accesso di Lync vengono in genere configurate automaticamente quando viene installato Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-106">Your Lync sign-in information is usually configured automatically when Lync 2013 is installed.</span></span> <span data-ttu-id="dd2fb-107">Tuttavia, la prima volta che si utilizza Lync, potrebbe essere necessario avviare manualmente il client.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-107">But the first time you use Lync, you might have to manually start the client.</span></span>

<span data-ttu-id="dd2fb-108">**Per accedere a Lync per la prima volta**</span><span class="sxs-lookup"><span data-stu-id="dd2fb-108">**To sign in to Lync for the first time**</span></span>

1.  <span data-ttu-id="dd2fb-109">Accedere alla rete dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-109">Log on to your organization’s network.</span></span>

2.  <span data-ttu-id="dd2fb-110">Selezionare **Avvia** \> **tutti i programmi** \> **Microsoft \> Lync Lync 2013**.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-110">Select **Start** \> **All Programs** \> **Microsoft Lync \> Lync 2013**.</span></span>
    
    <span data-ttu-id="dd2fb-111">Verrà visualizzata la schermata di accesso di Lync.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-111">You should see the Lync sign-in screen.</span></span>
    
      - <span data-ttu-id="dd2fb-112">Se la casella indirizzo di accesso è già stata compilata, verificare che l'indirizzo visualizzato sia corretto.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-112">If the sign-in address box is already filled in, confirm that the address shown is correct.</span></span>
    
      - <span data-ttu-id="dd2fb-113">Se non è corretto o se la casella è vuota, immettere l'indirizzo di accesso di Lync (in genere corrisponde all'indirizzo di posta elettronica).</span><span class="sxs-lookup"><span data-stu-id="dd2fb-113">If it’s not correct, or if the box is empty, enter your Lync sign-in address (this is usually the same as your email address).</span></span>
    
      - <span data-ttu-id="dd2fb-114">Se viene visualizzata una casella password vuota, aggiungere la password.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-114">If an empty password box is displayed, add your password.</span></span>

3.  <span data-ttu-id="dd2fb-115">Selezionare **accesso**.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-115">Select **Sign-in**.</span></span>

</div>

<div>

## <a name="sign-out-of-lync"></a><span data-ttu-id="dd2fb-116">Disconnessione di Lync</span><span class="sxs-lookup"><span data-stu-id="dd2fb-116">Sign out of Lync</span></span>

<span data-ttu-id="dd2fb-117">Al termine dell'utilizzo di Lync, è possibile chiudere la visualizzazione, disconnettersi dalla sessione o uscire dal programma, tutto dal menu file.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-117">When you’re finished using Lync, you can close the display, sign out of your session, or exit from the program, all from the File menu.</span></span> <span data-ttu-id="dd2fb-118">Nella tabella seguente vengono illustrate le differenze tra le opzioni.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-118">The following table explains the differences in the options.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dd2fb-119">Opzione</span><span class="sxs-lookup"><span data-stu-id="dd2fb-119">Option</span></span></th>
<th><span data-ttu-id="dd2fb-120">Funzione</span><span class="sxs-lookup"><span data-stu-id="dd2fb-120">What it does</span></span></th>
<th><span data-ttu-id="dd2fb-121">Modalità di esecuzione</span><span class="sxs-lookup"><span data-stu-id="dd2fb-121">How to perform it</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dd2fb-122">Chiudere</span><span class="sxs-lookup"><span data-stu-id="dd2fb-122">Close</span></span></p></td>
<td><p><span data-ttu-id="dd2fb-123">Chiude la visualizzazione di Lync ma consente di continuare a eseguire la sessione di Lync identificata con l'ID utente.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-123">Closes your Lync display but lets the Lync session identified with your user ID continue to run.</span></span> <span data-ttu-id="dd2fb-124">In questo modo è possibile continuare a ricevere notifiche e interagire con altri utenti.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-124">This is so you can continue to get notifications and interact with others.</span></span></p>
<p><span data-ttu-id="dd2fb-125">È possibile ottenere la visualizzazione in qualsiasi momento facendo clic sull'icona di Lync sulla barra delle applicazioni o nell'area di notifica nella parte inferiore dello schermo.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-125">You can get the display back at any time by clicking the Lync icon on the taskbar or the notification area at the bottom of your screen.</span></span></p></td>
<td><p><span data-ttu-id="dd2fb-126">Nella finestra principale di Lync eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dd2fb-126">On the Lync main window, do one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="dd2fb-127">Selezionare il pulsante <strong>Opzioni</strong> , quindi fare clic su <strong>Chiudi</strong> <strong>file</strong> &gt; .</span><span class="sxs-lookup"><span data-stu-id="dd2fb-127">Select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Close</strong>.</span></span></p></li>
<li><p><span data-ttu-id="dd2fb-128">Fare clic sul pulsante <strong>Chiudi</strong> (X) nell'angolo in alto a destra della finestra.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-128">Click the <strong>Close</strong> button (X) in the upper-right corner of the window.</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd2fb-129">Disconnessione</span><span class="sxs-lookup"><span data-stu-id="dd2fb-129">Sign out</span></span></p></td>
<td><p><span data-ttu-id="dd2fb-130">Termina la sessione di Lync associata all'ID utente, ma Lync continua a essere eseguito in background.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-130">Ends the Lync session associated with your user ID, but Lync continues to run in the background.</span></span> <span data-ttu-id="dd2fb-131">Quando si effettua l'accesso, verrà visualizzata la finestra di accesso.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-131">When you sign out, the sign-in window will appear.</span></span></p>
<div>

> [!TIP]  
> <span data-ttu-id="dd2fb-132">Selezionare <STRONG>Elimina le informazioni</STRONG> di accesso quando si effettua l'accesso per rimuovere il record dell'ID di accesso e della password dal computer.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-132">Select <STRONG>Delete my sign-in information</STRONG> when you sign out to remove the record of your logon ID and password from the computer.</span></span> <span data-ttu-id="dd2fb-133">In questo modo, è possibile facilitare la risoluzione dei problemi di accesso per il supporto alle persone.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-133">Doing this might make it easier for support people to troubleshoot sign-in issues.</span></span> <span data-ttu-id="dd2fb-134">È inoltre possibile garantire che le informazioni di accesso siano più sicure rendendo difficile per gli utenti non autorizzati l'accesso con le credenziali.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-134">It can also help ensure your sign-in information is more secure by making it difficult for unauthorized users to log on with your credentials.</span></span>


</div></td>
<td><p><span data-ttu-id="dd2fb-135">Nella finestra principale di Lync selezionare il pulsante <strong>Opzioni</strong> , quindi selezionare <strong>disconnessione</strong> <strong>file</strong> &gt; .</span><span class="sxs-lookup"><span data-stu-id="dd2fb-135">On the Lync main window, select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Sign Out</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd2fb-136">Uscita</span><span class="sxs-lookup"><span data-stu-id="dd2fb-136">Exit</span></span></p></td>
<td><p><span data-ttu-id="dd2fb-137">Termina la sessione di Lync e arresta Lync nel computer.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-137">Ends your Lync session and shuts down Lync on your computer.</span></span> <span data-ttu-id="dd2fb-138">Dopo l'uscita, se si desidera riavviare Lync, selezionare <strong>Avvia</strong> &gt; <strong>tutti i programmi</strong> &gt; <strong>Microsoft Lync</strong> &gt; <strong>Lync 2013</strong>.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-138">After exiting, if you want to restart Lync, select <strong>Start</strong> &gt; <strong>All Programs</strong> &gt; <strong>Microsoft Lync</strong> &gt; <strong>Lync 2013</strong>.</span></span></p></td>
<td><p><span data-ttu-id="dd2fb-139">Nella finestra principale di Lync, selezionare il pulsante <strong>Opzioni</strong> , quindi selezionare <strong></strong> &gt; <strong>Esci</strong>file.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-139">On the Lync main window, select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Exit</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sign-in-to-lync-with-a-smart-card"></a><span data-ttu-id="dd2fb-140">Accedere a Lync con una smart card</span><span class="sxs-lookup"><span data-stu-id="dd2fb-140">Sign in to Lync with a Smart Card</span></span>

<span data-ttu-id="dd2fb-141">Alcune organizzazioni ora utilizzano un processo di accesso a più passaggi, denominato autenticazione a due fattori, per aumentare la sicurezza per gli utenti di Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-141">Some organizations now use a multi-step sign-in process, called two-factor authentication, to increase security for their Lync 2013 users.</span></span> <span data-ttu-id="dd2fb-142">Se si prevede di utilizzare questa opzione, sarà necessario disporre di una "smart card" per accedere a Lync.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-142">If you’re expected to use this option, you’ll need a “smart card” to sign in to Lync.</span></span> <span data-ttu-id="dd2fb-143">Le smart card sono disponibili in due tipi, fisico e virtuale:</span><span class="sxs-lookup"><span data-stu-id="dd2fb-143">Smart cards come in two varieties, physical and virtual:</span></span>

  - <span data-ttu-id="dd2fb-144">**Fisica**   delle dimensioni di una carta di credito.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-144">**Physical**   About the size of a credit card.</span></span> <span data-ttu-id="dd2fb-145">È possibile inserirlo in un lettore di smart card quando si effettua l'accesso.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-145">You insert it into a smart card reader when you log in.</span></span>

  - <span data-ttu-id="dd2fb-146">**Virtual**   non è un oggetto fisico, ma un identificatore elettronico che viene scritto in un chip speciale sul computer, che in sostanza crea la smart card nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-146">**Virtual**   Not a physical object, but an electronic identifier that gets written to a special chip on your computer, which in essence builds the smart card into your computer.</span></span> <span data-ttu-id="dd2fb-147">Disponibile solo per l'utilizzo con i computer Windows 8 che contengono il chip TPM (Trusted Platform Module).</span><span class="sxs-lookup"><span data-stu-id="dd2fb-147">Available only for use with Windows 8 computers that contain the TPM (Trusted Platform Module) chip.</span></span>

<div>

## <a name="enroll-your-smart-card"></a><span data-ttu-id="dd2fb-148">Registrare la smart card</span><span class="sxs-lookup"><span data-stu-id="dd2fb-148">Enroll your smart card</span></span>

<span data-ttu-id="dd2fb-149">Prima di poter accedere con una smart card, è necessario che la scheda sia "registrazione", ovvero che le credenziali utente debbano essere identificate con la scheda.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-149">Before you can sign in with a smart card, the card must be “enrolled”—that is, your user credentials have to be identified with the card.</span></span> <span data-ttu-id="dd2fb-150">Questo è il caso se la scheda è fisica o virtuale.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-150">This is the case whether the card is physical or virtual.</span></span> <span data-ttu-id="dd2fb-151">Questo processo potrebbe essere già stato eseguito dall'amministratore di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-151">This process may already been carried out by your Lync Server administrator.</span></span> <span data-ttu-id="dd2fb-152">Verifica se non si è certi che l'operazione sia stata completata.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-152">Check with them if you’re not sure whether that has been done.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dd2fb-153">Poiché ogni smart card virtuale è associata solo al dispositivo in cui è installato, sarà necessario registrare una scheda separata per ogni computer Windows 8 utilizzato.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-153">Since each virtual smart card is associated only with the device it’s installed on, a separate card will need to be enrolled for each Windows 8 computer you use.</span></span>



</div>

<span data-ttu-id="dd2fb-154">**Per registrare manualmente la smart card**</span><span class="sxs-lookup"><span data-stu-id="dd2fb-154">**To manually enroll your smart card**</span></span>

1.  <span data-ttu-id="dd2fb-155">Eseguire l'accesso al computer in cui verrà eseguito Lync.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-155">Log on to the computer you’ll be running Lync on.</span></span>

2.  <span data-ttu-id="dd2fb-156">Tramite Internet Explorer, passare alla pagina di registrazione Web dell'autorità di certificazione dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-156">Using Internet Explorer, browse to your organization’s Certificate Authority Web Enrollment page.</span></span>
    
    <span data-ttu-id="dd2fb-157">Rivolgersi all'amministratore di Lync Server per l'indirizzo Web di questa risorsa se non è già presente.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-157">Ask your Lync Server administrator for the web address of this resource if you don’t already have it.</span></span> <span data-ttu-id="dd2fb-158">L'URL avrà un aspetto analogo al https://MyCA.\seguente:\][YourCompanyName. com/certsrv.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-158">The URL will look something like this: https://MyCA.\[yourcompanyname\].com/certsrv.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dd2fb-159">Se si utilizza Internet Explorer 10, potrebbe essere necessario visualizzare questo sito Web in modalità compatibilità.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-159">If you’re using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

    
    </div>

3.  <span data-ttu-id="dd2fb-160">Quando viene richiesto di accedere alla pagina certificazione, eseguire l'accesso utilizzando l'account di dominio (anziché l'amministratore del computer).</span><span class="sxs-lookup"><span data-stu-id="dd2fb-160">When you’re prompted to log on to the certification page, log on using your domain account (rather than as administrator of your computer).</span></span>

4.  <span data-ttu-id="dd2fb-161">Nella pagina di benvenuto del sito Web, selezionare **Richiedi un certificato**.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-161">On the website Welcome Page, select **Request a certificate**.</span></span>

5.  <span data-ttu-id="dd2fb-162">Selezionare **richiesta avanzata**.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-162">Select **Advanced Request**.</span></span>

6.  <span data-ttu-id="dd2fb-163">Selezionare **Crea e invia una richiesta all'autorità di certificazione**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-163">Select **Create and submit a request to this CA**, then click **Next**.</span></span>

7.  <span data-ttu-id="dd2fb-164">Verrà visualizzata una pagina denominata stazione di registrazione smart card.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-164">Now you’ll see a page called Smart Card Enrollment Station.</span></span> <span data-ttu-id="dd2fb-165">Approvare la richiesta di installazione del controllo ActiveX e quindi completare il modulo di richiesta Advanced Certificate come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="dd2fb-165">Approve the request to install the ActiveX control, and then complete the Advanced Certificate Request form as follows:</span></span>
    
    1.  <span data-ttu-id="dd2fb-166">Selezionare **utente smartcard** nell'elenco a discesa **modello di certificato** .</span><span class="sxs-lookup"><span data-stu-id="dd2fb-166">Select **Smartcard user** from the **Certificate Template** dropdown list.</span></span>
    
    2.  <span data-ttu-id="dd2fb-167">Selezionare **Crea nuovo set di chiavi**.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-167">Select **Create new key set**.</span></span>
    
    3.  <span data-ttu-id="dd2fb-168">Trovare le informazioni sul produttore nell'etichetta della smart card e selezionarlo nell'elenco a discesa **CSP** .</span><span class="sxs-lookup"><span data-stu-id="dd2fb-168">Find the manufacturer information on the label of your smart card and select that manufacturer from the **CSP** dropdown list.</span></span>
    
    4.  <span data-ttu-id="dd2fb-169">Selezionare **CSP** come formato di richiesta, se non è già selezionato.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-169">Select **CSP** as the Request Format, if it’s not already selected.</span></span>
    
    5.  <span data-ttu-id="dd2fb-170">Selezionare **SHA1** dall'elenco a discesa dell'algoritmo hash, se non è già selezionato.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-170">Select **sha1** from the Hash Algorithm dropdown list, if it’s not already selected.</span></span>
    
    6.  <span data-ttu-id="dd2fb-171">Assegnare un nome al certificato che si desidera riconoscere e fare clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-171">Give your certificate a name you’ll recognize, and click **Submit**.</span></span>

8.  <span data-ttu-id="dd2fb-172">A questo punto, inserire la smart card vuota nel lettore di schede collegato alla stazione di registrazione e fare clic su **registra**.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-172">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>

9.  <span data-ttu-id="dd2fb-173">Quando richiesto, immettere il proprio PIN (Personal Identification Number) e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-173">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dd2fb-174">Se la persona del supporto tecnico non ha fornito un PIN speciale da utilizzare per registrare la smart card, utilizzare il valore del PIN della smart card predefinita, che è 12345678.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-174">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span>

    
    </div>

10. <span data-ttu-id="dd2fb-175">Selezionare l'opzione per imporre all'utente di modificare il PIN al primo utilizzo della smart card.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-175">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>

11. <span data-ttu-id="dd2fb-176">A questo punto, inserire la smart card vuota nel lettore di schede collegato alla stazione di registrazione e fare clic su **registra**.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-176">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>

12. <span data-ttu-id="dd2fb-177">Quando richiesto, immettere il proprio PIN (Personal Identification Number) e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-177">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dd2fb-178">Se la persona del supporto tecnico non ha fornito un PIN speciale da utilizzare per registrare la smart card, utilizzare il valore del PIN della smart card predefinita, che è 12345678.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-178">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span>

    
    </div>

13. <span data-ttu-id="dd2fb-179">Selezionare l'opzione per imporre all'utente di modificare il PIN al primo utilizzo della smart card.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-179">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>

14. <span data-ttu-id="dd2fb-180">Fare clic su **OK** per confermare che il certificato visualizzato contiene le informazioni su di esso.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-180">Click **OK** to confirm that the certificate displayed has your information on it.</span></span>

15. <span data-ttu-id="dd2fb-181">Dopo aver visualizzato l'avviso che il certificato è stato emesso, fare clic su **installa questo certificato** per completare il processo di registrazione.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-181">Once you see the notice that the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>

</div>

<div>

## <a name="sign-in-to-lync-with-your-smart-card-credentials"></a><span data-ttu-id="dd2fb-182">Accedere a Lync con le credenziali smart card</span><span class="sxs-lookup"><span data-stu-id="dd2fb-182">Sign in to Lync with your smart card credentials</span></span>

<span data-ttu-id="dd2fb-183">Prima di utilizzare la smart card per la prima volta, si consiglia di fare clic su **Elimina le informazioni di accesso** nella pagina di accesso di Lync.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-183">Before you use your smart card for the first time, it’s recommended that you click **Delete my sign-in info** on the Lync sign-in page.</span></span> <span data-ttu-id="dd2fb-184">In questo modo vengono cancellate le credenziali di accesso archiviate nel computer e viene eliminata una possibile origine di errore.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-184">Doing this clears any sign-in credentials stored on your computer, and eliminates a possible source of error.</span></span>

<span data-ttu-id="dd2fb-185">**Per accedere a Lync con le credenziali smart card**</span><span class="sxs-lookup"><span data-stu-id="dd2fb-185">**To sign in to Lync with your smart card credentials**</span></span>

1.  <span data-ttu-id="dd2fb-186">Avviare il client Lync.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-186">Start the Lync client.</span></span>

2.  <span data-ttu-id="dd2fb-187">Nella schermata di accesso digitare il nome dell'account utente di accesso nella casella **indirizzo di accesso** e quindi fare clic su **Accedi**.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-187">On the Sign in screen, type your sign in user account name in the **Sign-in address** box, and then click **Sign In**.</span></span>

3.  <span data-ttu-id="dd2fb-188">Se si utilizza una smart card virtuale, ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-188">If you are using a virtual smart card, skip this step.</span></span>
    
    <span data-ttu-id="dd2fb-189">Se si utilizza una smart card fisica, inserire la smart card nel lettore di smart card e quindi fare clic su **OK** quando la scheda viene rilevata.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-189">If you are using a physical smart card, insert the smart card into your smart card reader and prompted to do so, and then click **OK** when the card is detected.</span></span>

4.  <span data-ttu-id="dd2fb-190">Digitare il numero di PIN per la smart card e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-190">Type in the PIN number you for your smart card and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dd2fb-191">Se non è stato assegnato un numero PIN della smart card dalla persona di supporto, utilizzare il valore predefinito, che è 12345678.</span><span class="sxs-lookup"><span data-stu-id="dd2fb-191">If you were not assigned a smart card PIN number by your support person, use the default value, which is 12345678.</span></span>

    
    </div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

