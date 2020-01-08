---
title: "Lync Server 2013: utilizzo dell'autenticazione a due fattori con il client Lync"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using two-factor authentication with Lync client
ms:assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn338071(v=OCS.15)
ms:contentKeyID: 55115593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5af9e9b5268fd218bfe5856473124514cfe34945
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980855"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-two-factor-authentication-with-lync-client-and-lync-server-2013"></a><span data-ttu-id="55474-102">Uso dell'autenticazione a due fattori con Lync client e Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55474-102">Using two-factor authentication with Lync client and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55474-103">_**Argomento Ultima modifica:** 2013-07-11_</span><span class="sxs-lookup"><span data-stu-id="55474-103">_**Topic Last Modified:** 2013-07-11_</span></span>

<span data-ttu-id="55474-104">Questo argomento descrive come sfruttare l'autenticazione a due fattori con il client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="55474-104">This topic described how to take advantage of two-factor authentication with Lync 2013 client.</span></span>

<div>

## <a name="sign-in-to-lync-2013-for-the-first-time"></a><span data-ttu-id="55474-105">Accedere a Lync 2013 per la prima volta</span><span class="sxs-lookup"><span data-stu-id="55474-105">Sign in to Lync 2013 for the first time</span></span>

<span data-ttu-id="55474-106">Le informazioni di accesso di Lync vengono in genere configurate automaticamente al momento dell'installazione di Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="55474-106">Your Lync sign-in information is usually configured automatically when Lync 2013 is installed.</span></span> <span data-ttu-id="55474-107">Ma la prima volta che si usa Lync, potrebbe essere necessario avviare manualmente il client.</span><span class="sxs-lookup"><span data-stu-id="55474-107">But the first time you use Lync, you might have to manually start the client.</span></span>

<span data-ttu-id="55474-108">**Per accedere a Lync per la prima volta**</span><span class="sxs-lookup"><span data-stu-id="55474-108">**To sign in to Lync for the first time**</span></span>

1.  <span data-ttu-id="55474-109">Accedere alla rete dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="55474-109">Log on to your organization’s network.</span></span>

2.  <span data-ttu-id="55474-110">Selezionare **Avvia** \> **tutti i programmi** \> **Microsoft \> Lync Lync 2013**.</span><span class="sxs-lookup"><span data-stu-id="55474-110">Select **Start** \> **All Programs** \> **Microsoft Lync \> Lync 2013**.</span></span>
    
    <span data-ttu-id="55474-111">La schermata di accesso di Lync dovrebbe essere visualizzata.</span><span class="sxs-lookup"><span data-stu-id="55474-111">You should see the Lync sign-in screen.</span></span>
    
      - <span data-ttu-id="55474-112">Se la casella indirizzo di accesso è già stata compilata, verificare che l'indirizzo visualizzato sia corretto.</span><span class="sxs-lookup"><span data-stu-id="55474-112">If the sign-in address box is already filled in, confirm that the address shown is correct.</span></span>
    
      - <span data-ttu-id="55474-113">Se non è corretto o se la casella è vuota, immettere l'indirizzo di accesso di Lync (in genere corrisponde all'indirizzo di posta elettronica).</span><span class="sxs-lookup"><span data-stu-id="55474-113">If it’s not correct, or if the box is empty, enter your Lync sign-in address (this is usually the same as your email address).</span></span>
    
      - <span data-ttu-id="55474-114">Se viene visualizzata una casella password vuota, aggiungere la password.</span><span class="sxs-lookup"><span data-stu-id="55474-114">If an empty password box is displayed, add your password.</span></span>

3.  <span data-ttu-id="55474-115">Selezionare **Accedi**.</span><span class="sxs-lookup"><span data-stu-id="55474-115">Select **Sign-in**.</span></span>

</div>

<div>

## <a name="sign-out-of-lync"></a><span data-ttu-id="55474-116">Disconnettersi da Lync</span><span class="sxs-lookup"><span data-stu-id="55474-116">Sign out of Lync</span></span>

<span data-ttu-id="55474-117">Dopo aver completato l'uso di Lync, è possibile chiudere la visualizzazione, disconnettersi dalla sessione o uscire dal menu file.</span><span class="sxs-lookup"><span data-stu-id="55474-117">When you’re finished using Lync, you can close the display, sign out of your session, or exit from the program, all from the File menu.</span></span> <span data-ttu-id="55474-118">La tabella seguente illustra le differenze tra le opzioni.</span><span class="sxs-lookup"><span data-stu-id="55474-118">The following table explains the differences in the options.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="55474-119">Opzione</span><span class="sxs-lookup"><span data-stu-id="55474-119">Option</span></span></th>
<th><span data-ttu-id="55474-120">Cosa fa</span><span class="sxs-lookup"><span data-stu-id="55474-120">What it does</span></span></th>
<th><span data-ttu-id="55474-121">Come eseguirlo</span><span class="sxs-lookup"><span data-stu-id="55474-121">How to perform it</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="55474-122">Vicino</span><span class="sxs-lookup"><span data-stu-id="55474-122">Close</span></span></p></td>
<td><p><span data-ttu-id="55474-123">Chiude la visualizzazione Lync ma consente di continuare a eseguire la sessione Lync identificata con l'ID utente.</span><span class="sxs-lookup"><span data-stu-id="55474-123">Closes your Lync display but lets the Lync session identified with your user ID continue to run.</span></span> <span data-ttu-id="55474-124">In questo modo puoi continuare a ricevere notifiche e interagire con altri utenti.</span><span class="sxs-lookup"><span data-stu-id="55474-124">This is so you can continue to get notifications and interact with others.</span></span></p>
<p><span data-ttu-id="55474-125">È possibile ripristinare la visualizzazione in qualsiasi momento facendo clic sull'icona di Lync nella barra delle applicazioni o nell'area di notifica nella parte inferiore dello schermo.</span><span class="sxs-lookup"><span data-stu-id="55474-125">You can get the display back at any time by clicking the Lync icon on the taskbar or the notification area at the bottom of your screen.</span></span></p></td>
<td><p><span data-ttu-id="55474-126">Nella finestra principale di Lync eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="55474-126">On the Lync main window, do one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="55474-127">Selezionare il pulsante <strong>Opzioni</strong> , quindi selezionare <strong>file</strong> &gt; <strong>Chiudi</strong>.</span><span class="sxs-lookup"><span data-stu-id="55474-127">Select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Close</strong>.</span></span></p></li>
<li><p><span data-ttu-id="55474-128">Fare clic sul pulsante <strong>Chiudi</strong> (X) nell'angolo in alto a destra della finestra.</span><span class="sxs-lookup"><span data-stu-id="55474-128">Click the <strong>Close</strong> button (X) in the upper-right corner of the window.</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55474-129">Disconnettersi</span><span class="sxs-lookup"><span data-stu-id="55474-129">Sign out</span></span></p></td>
<td><p><span data-ttu-id="55474-130">Termina la sessione Lync associata all'ID utente, ma Lync continua a essere eseguito in background.</span><span class="sxs-lookup"><span data-stu-id="55474-130">Ends the Lync session associated with your user ID, but Lync continues to run in the background.</span></span> <span data-ttu-id="55474-131">Quando ci si disconnette, verrà visualizzata la finestra di accesso.</span><span class="sxs-lookup"><span data-stu-id="55474-131">When you sign out, the sign-in window will appear.</span></span></p>
<div>

> [!TIP]  
> <span data-ttu-id="55474-132">Selezionare <STRONG>Elimina le informazioni</STRONG> di accesso quando si esce per rimuovere il record dell'ID di accesso e della password dal computer.</span><span class="sxs-lookup"><span data-stu-id="55474-132">Select <STRONG>Delete my sign-in information</STRONG> when you sign out to remove the record of your logon ID and password from the computer.</span></span> <span data-ttu-id="55474-133">In questo modo, puoi semplificare la risoluzione dei problemi di accesso per il supporto delle persone.</span><span class="sxs-lookup"><span data-stu-id="55474-133">Doing this might make it easier for support people to troubleshoot sign-in issues.</span></span> <span data-ttu-id="55474-134">Può anche essere utile garantire che le informazioni di accesso siano più sicure, rendendo difficile per gli utenti non autorizzati l'accesso con le credenziali.</span><span class="sxs-lookup"><span data-stu-id="55474-134">It can also help ensure your sign-in information is more secure by making it difficult for unauthorized users to log on with your credentials.</span></span>


</div></td>
<td><p><span data-ttu-id="55474-135">Nella finestra principale di Lync selezionare il pulsante <strong>Opzioni</strong> e quindi fare clic su <strong>Disconnetti</strong> <strong>file</strong> &gt; .</span><span class="sxs-lookup"><span data-stu-id="55474-135">On the Lync main window, select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Sign Out</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55474-136">Uscita</span><span class="sxs-lookup"><span data-stu-id="55474-136">Exit</span></span></p></td>
<td><p><span data-ttu-id="55474-137">Termina la sessione di Lync e arresta Lync nel computer.</span><span class="sxs-lookup"><span data-stu-id="55474-137">Ends your Lync session and shuts down Lync on your computer.</span></span> <span data-ttu-id="55474-138">Dopo l'uscita, se si vuole riavviare Lync, selezionare <strong>Avvia</strong> &gt; <strong>tutti i programmi</strong> &gt; <strong>Microsoft Lync</strong> &gt; <strong>Lync 2013</strong>.</span><span class="sxs-lookup"><span data-stu-id="55474-138">After exiting, if you want to restart Lync, select <strong>Start</strong> &gt; <strong>All Programs</strong> &gt; <strong>Microsoft Lync</strong> &gt; <strong>Lync 2013</strong>.</span></span></p></td>
<td><p><span data-ttu-id="55474-139">Nella finestra principale di Lync selezionare il pulsante <strong>Opzioni</strong> e quindi selezionare Esci <strong>file</strong> &gt; <strong></strong>.</span><span class="sxs-lookup"><span data-stu-id="55474-139">On the Lync main window, select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Exit</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sign-in-to-lync-with-a-smart-card"></a><span data-ttu-id="55474-140">Accedere a Lync con una smart card</span><span class="sxs-lookup"><span data-stu-id="55474-140">Sign in to Lync with a Smart Card</span></span>

<span data-ttu-id="55474-141">Alcune organizzazioni usano ora un processo di accesso a più passaggi, denominato autenticazione a due fattori, per aumentare la sicurezza per gli utenti di Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="55474-141">Some organizations now use a multi-step sign-in process, called two-factor authentication, to increase security for their Lync 2013 users.</span></span> <span data-ttu-id="55474-142">Se si prevede di usare questa opzione, è necessaria una "smart card" per accedere a Lync.</span><span class="sxs-lookup"><span data-stu-id="55474-142">If you’re expected to use this option, you’ll need a “smart card” to sign in to Lync.</span></span> <span data-ttu-id="55474-143">Le smart card sono disponibili in due tipi, fisico e virtuale:</span><span class="sxs-lookup"><span data-stu-id="55474-143">Smart cards come in two varieties, physical and virtual:</span></span>

  - <span data-ttu-id="55474-144">**Fisiche**   delle dimensioni di una carta di credito.</span><span class="sxs-lookup"><span data-stu-id="55474-144">**Physical**   About the size of a credit card.</span></span> <span data-ttu-id="55474-145">Quando si effettua l'accesso, è possibile inserirla in un lettore di smart card.</span><span class="sxs-lookup"><span data-stu-id="55474-145">You insert it into a smart card reader when you log in.</span></span>

  - <span data-ttu-id="55474-146">**Virtual**   non è un oggetto fisico, ma un identificatore elettronico che viene scritto in un chip speciale nel computer, che in sostanza crea la smart card nel computer.</span><span class="sxs-lookup"><span data-stu-id="55474-146">**Virtual**   Not a physical object, but an electronic identifier that gets written to a special chip on your computer, which in essence builds the smart card into your computer.</span></span> <span data-ttu-id="55474-147">Disponibile solo per l'uso con i computer Windows 8 che contengono il chip TPM (Trusted Platform Module).</span><span class="sxs-lookup"><span data-stu-id="55474-147">Available only for use with Windows 8 computers that contain the TPM (Trusted Platform Module) chip.</span></span>

<div>

## <a name="enroll-your-smart-card"></a><span data-ttu-id="55474-148">Registrare la smart card</span><span class="sxs-lookup"><span data-stu-id="55474-148">Enroll your smart card</span></span>

<span data-ttu-id="55474-149">Prima di poter accedere con una smart card, la scheda deve essere "registrata", ovvero le credenziali utente devono essere identificate con la scheda.</span><span class="sxs-lookup"><span data-stu-id="55474-149">Before you can sign in with a smart card, the card must be “enrolled”—that is, your user credentials have to be identified with the card.</span></span> <span data-ttu-id="55474-150">Questo è il caso che la carta sia fisica o virtuale.</span><span class="sxs-lookup"><span data-stu-id="55474-150">This is the case whether the card is physical or virtual.</span></span> <span data-ttu-id="55474-151">Questo processo può essere già eseguito dall'amministratore di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="55474-151">This process may already been carried out by your Lync Server administrator.</span></span> <span data-ttu-id="55474-152">Verificare se non si è certi che sia stato fatto.</span><span class="sxs-lookup"><span data-stu-id="55474-152">Check with them if you’re not sure whether that has been done.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="55474-153">Poiché ogni smart card virtuale è associata solo al dispositivo in cui è installato, sarà necessario registrare una scheda separata per ogni computer Windows 8 usato.</span><span class="sxs-lookup"><span data-stu-id="55474-153">Since each virtual smart card is associated only with the device it’s installed on, a separate card will need to be enrolled for each Windows 8 computer you use.</span></span>



</div>

<span data-ttu-id="55474-154">**Per registrare manualmente la smart card**</span><span class="sxs-lookup"><span data-stu-id="55474-154">**To manually enroll your smart card**</span></span>

1.  <span data-ttu-id="55474-155">Accedere al computer in cui verrà eseguito Lync.</span><span class="sxs-lookup"><span data-stu-id="55474-155">Log on to the computer you’ll be running Lync on.</span></span>

2.  <span data-ttu-id="55474-156">Usando Internet Explorer, passare alla pagina di registrazione Web dell'autorità di certificazione dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="55474-156">Using Internet Explorer, browse to your organization’s Certificate Authority Web Enrollment page.</span></span>
    
    <span data-ttu-id="55474-157">Rivolgersi all'amministratore di Lync Server per l'indirizzo Web della risorsa, se non è già disponibile.</span><span class="sxs-lookup"><span data-stu-id="55474-157">Ask your Lync Server administrator for the web address of this resource if you don’t already have it.</span></span> <span data-ttu-id="55474-158">L'URL avrà un aspetto simile al seguente https://MyCA.\: [\]NomeSocietà. com/certsrv.</span><span class="sxs-lookup"><span data-stu-id="55474-158">The URL will look something like this: https://MyCA.\[yourcompanyname\].com/certsrv.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="55474-159">Se si usa Internet Explorer 10, potrebbe essere necessario visualizzare il sito Web in modalità compatibilità.</span><span class="sxs-lookup"><span data-stu-id="55474-159">If you’re using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

    
    </div>

3.  <span data-ttu-id="55474-160">Quando viene richiesto di accedere alla pagina certificazione, accedere con l'account di dominio (anziché come amministratore del computer).</span><span class="sxs-lookup"><span data-stu-id="55474-160">When you’re prompted to log on to the certification page, log on using your domain account (rather than as administrator of your computer).</span></span>

4.  <span data-ttu-id="55474-161">Nella pagina di benvenuto del sito Web selezionare **Richiedi un certificato**.</span><span class="sxs-lookup"><span data-stu-id="55474-161">On the website Welcome Page, select **Request a certificate**.</span></span>

5.  <span data-ttu-id="55474-162">Selezionare **richiesta avanzata**.</span><span class="sxs-lookup"><span data-stu-id="55474-162">Select **Advanced Request**.</span></span>

6.  <span data-ttu-id="55474-163">Selezionare **Crea e inviare una richiesta alla CA**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="55474-163">Select **Create and submit a request to this CA**, then click **Next**.</span></span>

7.  <span data-ttu-id="55474-164">Ora verrà visualizzata una pagina denominata stazione di registrazione smart card.</span><span class="sxs-lookup"><span data-stu-id="55474-164">Now you’ll see a page called Smart Card Enrollment Station.</span></span> <span data-ttu-id="55474-165">Approva la richiesta di installazione del controllo ActiveX e quindi compila il modulo di richiesta Advanced Certificate nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="55474-165">Approve the request to install the ActiveX control, and then complete the Advanced Certificate Request form as follows:</span></span>
    
    1.  <span data-ttu-id="55474-166">Selezionare **utente smartcard** nell'elenco a discesa **modello di certificato** .</span><span class="sxs-lookup"><span data-stu-id="55474-166">Select **Smartcard user** from the **Certificate Template** dropdown list.</span></span>
    
    2.  <span data-ttu-id="55474-167">Selezionare **Crea nuovo set di tasti**.</span><span class="sxs-lookup"><span data-stu-id="55474-167">Select **Create new key set**.</span></span>
    
    3.  <span data-ttu-id="55474-168">Trovare le informazioni sul produttore nell'etichetta della smart card e selezionare tale produttore nell'elenco a discesa **CSP** .</span><span class="sxs-lookup"><span data-stu-id="55474-168">Find the manufacturer information on the label of your smart card and select that manufacturer from the **CSP** dropdown list.</span></span>
    
    4.  <span data-ttu-id="55474-169">Selezionare **CSP** come formato di richiesta, se non è già selezionato.</span><span class="sxs-lookup"><span data-stu-id="55474-169">Select **CSP** as the Request Format, if it’s not already selected.</span></span>
    
    5.  <span data-ttu-id="55474-170">Selezionare **SHA1** nell'elenco a discesa algoritmo hash, se non è già selezionato.</span><span class="sxs-lookup"><span data-stu-id="55474-170">Select **sha1** from the Hash Algorithm dropdown list, if it’s not already selected.</span></span>
    
    6.  <span data-ttu-id="55474-171">Assegnare un nome al certificato che verrà riconosciuto e quindi fare clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="55474-171">Give your certificate a name you’ll recognize, and click **Submit**.</span></span>

8.  <span data-ttu-id="55474-172">Inserire ora la smart card vuota nel lettore di schede collegata alla stazione di registrazione e fare clic su **registra**.</span><span class="sxs-lookup"><span data-stu-id="55474-172">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>

9.  <span data-ttu-id="55474-173">Quando richiesto, immettere il PIN (Personal Identification Number) e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="55474-173">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="55474-174">Se la persona del supporto tecnico non ha ricevuto un PIN speciale da usare per la registrazione della smart card, usare il valore PIN della smart card predefinito, ovvero 12345678.</span><span class="sxs-lookup"><span data-stu-id="55474-174">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span>

    
    </div>

10. <span data-ttu-id="55474-175">Selezionare l'opzione per forzare l'utente a cambiare il PIN per la prima volta che viene usata la smart card.</span><span class="sxs-lookup"><span data-stu-id="55474-175">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>

11. <span data-ttu-id="55474-176">Inserire ora la smart card vuota nel lettore di schede collegata alla stazione di registrazione e fare clic su **registra**.</span><span class="sxs-lookup"><span data-stu-id="55474-176">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>

12. <span data-ttu-id="55474-177">Quando richiesto, immettere il PIN (Personal Identification Number) e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="55474-177">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="55474-178">Se la persona del supporto tecnico non ha ricevuto un PIN speciale da usare per la registrazione della smart card, usare il valore PIN della smart card predefinito, ovvero 12345678.</span><span class="sxs-lookup"><span data-stu-id="55474-178">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span>

    
    </div>

13. <span data-ttu-id="55474-179">Selezionare l'opzione per forzare l'utente a cambiare il PIN per la prima volta che viene usata la smart card.</span><span class="sxs-lookup"><span data-stu-id="55474-179">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>

14. <span data-ttu-id="55474-180">Fare clic su **OK** per confermare che il certificato visualizzato contiene le informazioni.</span><span class="sxs-lookup"><span data-stu-id="55474-180">Click **OK** to confirm that the certificate displayed has your information on it.</span></span>

15. <span data-ttu-id="55474-181">Quando viene visualizzato l'avviso che il certificato è stato emesso, fare clic su **installa questo certificato** per completare il processo di registrazione.</span><span class="sxs-lookup"><span data-stu-id="55474-181">Once you see the notice that the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>

</div>

<div>

## <a name="sign-in-to-lync-with-your-smart-card-credentials"></a><span data-ttu-id="55474-182">Accedere a Lync con le credenziali della smart card</span><span class="sxs-lookup"><span data-stu-id="55474-182">Sign in to Lync with your smart card credentials</span></span>

<span data-ttu-id="55474-183">Prima di usare la smart card per la prima volta, è consigliabile fare clic su **Elimina le informazioni di accesso** nella pagina di accesso di Lync.</span><span class="sxs-lookup"><span data-stu-id="55474-183">Before you use your smart card for the first time, it’s recommended that you click **Delete my sign-in info** on the Lync sign-in page.</span></span> <span data-ttu-id="55474-184">In questo modo vengono cancellate le credenziali di accesso archiviate nel computer e viene eliminata una possibile origine di errore.</span><span class="sxs-lookup"><span data-stu-id="55474-184">Doing this clears any sign-in credentials stored on your computer, and eliminates a possible source of error.</span></span>

<span data-ttu-id="55474-185">**Per accedere a Lync con le credenziali della smart card**</span><span class="sxs-lookup"><span data-stu-id="55474-185">**To sign in to Lync with your smart card credentials**</span></span>

1.  <span data-ttu-id="55474-186">Avviare il client Lync.</span><span class="sxs-lookup"><span data-stu-id="55474-186">Start the Lync client.</span></span>

2.  <span data-ttu-id="55474-187">Nella schermata di accesso digitare il nome dell'account utente di accesso nella casella **indirizzo di accesso** e quindi fare clic su **Accedi**.</span><span class="sxs-lookup"><span data-stu-id="55474-187">On the Sign in screen, type your sign in user account name in the **Sign-in address** box, and then click **Sign In**.</span></span>

3.  <span data-ttu-id="55474-188">Se si usa una smart card virtuale, ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="55474-188">If you are using a virtual smart card, skip this step.</span></span>
    
    <span data-ttu-id="55474-189">Se si usa una smart card fisica, inserire la smart card nel lettore di smart card e quindi fare clic su **OK** quando viene rilevata la scheda.</span><span class="sxs-lookup"><span data-stu-id="55474-189">If you are using a physical smart card, insert the smart card into your smart card reader and prompted to do so, and then click **OK** when the card is detected.</span></span>

4.  <span data-ttu-id="55474-190">Digitare il PIN number per la smart card e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="55474-190">Type in the PIN number you for your smart card and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="55474-191">Se il numero di PIN della smart card non è stato assegnato dalla persona di supporto, usare il valore predefinito, ovvero 12345678.</span><span class="sxs-lookup"><span data-stu-id="55474-191">If you were not assigned a smart card PIN number by your support person, use the default value, which is 12345678.</span></span>

    
    </div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

