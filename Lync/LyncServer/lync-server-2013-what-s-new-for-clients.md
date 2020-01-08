---
title: 'Lync Server 2013: Novità per i client'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: What's new for clients
ms:assetid: 5c144677-4d58-4fc3-8445-74b76c9fcf07
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204933(v=OCS.15)
ms:contentKeyID: 48184253
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edf37f68d0ea11e17a799956f285d8ca82eb2a27
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981952"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="whats-new-for-clients-in-lync-server-2013"></a>Novità per i client in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-19_

Microsoft Lync 2013 offre un'interfaccia utente riprogettata e importanti nuove funzionalità. Per gli amministratori, il client è ora incluso nel programma di installazione di Office, offrendo un approccio più snello alla distribuzione di Office e alla personalizzazione dei client nell'organizzazione.

<div>


> [!NOTE]  
> Per una visualizzazione illustrata degli aggiornamenti dell'interfaccia utente di Lync 2013, vedere "Novità di Lync 2013" <A href="http://go.microsoft.com/fwlink/?linkid=273885">http://go.microsoft.com/fwlink/?LinkId=273885</A>in.



</div>

<div>

## <a name="integration-with-office-setup"></a>Integrazione con l'installazione di Office

Il client Lync 2013 e il componente aggiuntivo riunione online per Lync 2013, che supporta la gestione delle riunioni dall'interno del client di messaggistica e collaborazione di Outlook, sono ora inclusi nel programma di installazione di Office 2013.

Nelle versioni precedenti di Lync e Office Communicator è possibile usare le proprietà di Windows Installer per personalizzare e controllare l'installazione di Office. Poiché Lync 2013 è integrato con l'installazione di Office, è possibile usare i metodi seguenti per personalizzare la configurazione di Lync 2013:

  - Usare lo strumento di personalizzazione di Office

  - Usare il file config. XML per eseguire attività di installazione

  - Usare le opzioni della riga di comando di configurazione

<div>


> [!NOTE]  
> Il programma di installazione di Lync 2013 non disinstalla versioni precedenti di Lync o Office Communicator. Il client Lync 2013 installa affiancato ad altri client Lync o Office Communicator



</div>

Per informazioni dettagliate, vedere [distribuzione di client Lync in Lync Server 2013](lync-server-2013-deploying-lync-clients.md).

</div>

<div>

## <a name="group-policy-deployment"></a>Distribuzione di criteri di gruppo

Poiché Lync 2013 è ora incluso nel programma di installazione di Office, il metodo per la distribuzione delle impostazioni dei criteri di gruppo di Lync è cambiato. Nelle versioni precedenti di Lync e Office Communicator si poteva usare Communicator. adm per definire le impostazioni dei criteri di gruppo, mentre in Lync 2013 è ora possibile usare i modelli di amministrazione ADMX e ADML di Lync forniti insieme ai criteri di gruppo di Office Modelli amministrativi.

Per informazioni dettagliate, vedere [impostazioni di criteri di gruppo per Lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md).

</div>

<div>

## <a name="outlook-scheduling-add-in-updates"></a>Aggiornamenti del componente aggiuntivo per la pianificazione di Outlook

Il componente aggiuntivo riunione online per Lync 2013 include la personalizzazione dell'invito alla riunione e le nuove opzioni della riunione.

  - Gli amministratori possono personalizzare gli inviti alle riunioni dell'organizzazione aggiungendo un logo personalizzato, un URL di supporto, un URL di dichiarazione di non responsabilità legale o un testo del piè di pagina personalizzato. Per informazioni dettagliate, vedere [personalizzazione del componente aggiuntivo riunione online in Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md).

  - I nuovi controlli di silenziamento dei partecipanti consentono agli organizzatori della riunione di pianificare le conferenze che hanno l'audio e il video dei partecipanti per impostazione predefinita.

</div>

<div>

## <a name="virtual-desktop-infrastructure-plug-in"></a>Plug-in infrastruttura desktop virtuale

Il client Lync 2013 ora supporta l'audio e il video in un ambiente VDI (Virtual Desktop Infrastructure). Un utente può connettere un dispositivo audio o video, ad esempio un auricolare o una fotocamera, al computer locale, ad esempio un thin client o un computer riutilizzato. L'utente può connettersi alla macchina virtuale, accedere al client Lync 2013 in esecuzione nella macchina virtuale e partecipare a comunicazioni audio e video in tempo reale, come se il client è in esecuzione localmente. Le caratteristiche seguenti sono supportate in un ambiente desktop virtuale:

  - Integrazione di dispositivi per audio e video, inclusi i seguenti:
    
      - Chiamare i controlli dal dispositivo
    
      - Integrazione della presenza nel dispositivo
    
      - Supporto di più HID (Human Interface Device)

  - Supporto per la posizione e i servizi di emergenza.

  - Supporto per tutte le modalità di Lync, tra cui messaggistica istantanea, audio, video, condivisione applicazioni, condivisione desktop, condivisione di PowerPoint, lavagna e trasferimento di file.

  - Supporto audio e video in chiamate da persona a persona e conferenze telefoniche.

Per informazioni sulla distribuzione del plug-in VDI, vedere [distribuzione del plug-in Lync VDI in Lync Server 2013](lync-server-2013-deploying-the-lync-vdi-plug-in.md).

</div>

<div>

## <a name="video-enhancements"></a>Miglioramenti video

Diverse nuove funzionalità migliorano significativamente l'esperienza video per i partecipanti alla conferenza.

  - Il video viene migliorato con il rilevamento dei volti e l'inquadratura intelligente, in modo che il video di un partecipante si muova per mantenerli al centro della cornice.

  - Il video ad alta definizione è ora supportato in chiamate a due parti e conferenze multiparte. Gli utenti possono provare risoluzioni fino a HD 1080P.

  - I partecipanti possono scegliere tra diversi layout delle riunioni: la visualizzazione raccolta Mostra tutte le immagini o i video dei partecipanti; La visualizzazione relatore Mostra il contenuto della riunione e solo il video o l'immagine del relatore corrente; La visualizzazione presentazione Mostra solo il contenuto della riunione; La visualizzazione compatta Mostra solo i controlli della riunione.

  - Con la nuova caratteristica raccolta, i partecipanti possono vedere più feed video contemporaneamente. Se la conferenza include più di cinque partecipanti, i feed video dei partecipanti più attivi verranno visualizzati nella riga superiore e le immagini verranno visualizzate per gli altri partecipanti.

  - I partecipanti possono usare il blocco video per selezionare uno o più feed video disponibili per essere sempre visibili.

  - I relatori possono usare la caratteristica Spotlight video per selezionare il feed video di una persona in modo che tutti i partecipanti alla riunione vedano solo questo partecipante.

</div>

<div>

## <a name="chat-room-integration"></a>Integrazione di chat room

Lync 2013 integra ora le funzionalità fornite in precedenza da Lync 2010 Group Chat. Un client di chat di gruppo separato non è più necessario.

  - Dall'interno di Lync 2013 gli utenti possono cercare chat room, aggiungere chat room ai loro contatti, monitorare l'attività delle chat room e leggere e pubblicare messaggi.

  - Gli utenti possono creare feed di argomenti in modo che vengano avvisati se qualcuno in una delle chat room aggiunge un post contenente parole chiave specifiche.

  - Con la nuova pagina delle opzioni della **chat persistente** , gli utenti possono impostare avvisi e suoni di notifica che si applicano quando le persone inviano messaggi alle chat room.

</div>

<div>

## <a name="lync-web-app-updates"></a>Aggiornamenti di Lync Web App

Lync Web App è il client di conferenza basato sul Web per le riunioni di Lync Server 2013. In questa versione, l'aggiunta di audio e video per computer a Lync Web App offre un'esperienza di riunione completa per tutti coloro che non hanno un client Lync installato localmente. I partecipanti alla riunione hanno accesso a tutte le caratteristiche di collaborazione e condivisione e ai controlli della riunione relatore.

Quando un utente tenta di partecipare a una riunione ma non ha un client installato localmente, viene aperta Lync Web App. Se si vogliono consentire altre opzioni per partecipare alla riunione, è possibile configurare la pagina di partecipazione alla riunione; vedere [configurazione della pagina di partecipazione alla riunione in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) nella documentazione relativa alla distribuzione.

A causa dei miglioramenti apportati a Lync Web App, una versione aggiornata di Attendeee non è disponibile per Lync Server 2013. Lync Web App è il client preferito per i partecipanti esterni all'organizzazione. Non è necessaria un'installazione client locale, anche se le funzionalità audio, video e condivisione richiedono un plug-in da installare al primo utilizzo.

</div>

<div>

## <a name="lync-2013-for-mobile-clients-updates"></a>Aggiornamenti di Lync 2013 per i client mobili

Oltre alla presenza avanzata, ai contatti e alle funzionalità di messaggistica istantanea, i client mobili di Lync 2013 ora supportano le chiamate vocali e video tramite Internet e le connessioni dati cellulari. Con un singolo tocco del collegamento alla riunione in un elemento del calendario, gli utenti di dispositivi mobili possono partecipare a riunioni vocali e video di Lync. Per altre informazioni sui client di Lync 2013 per dispositivi mobili, vedere [pianificazione per i client mobili in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).

</div>

<div>

## <a name="lync-2013-user-interface-updates"></a>Aggiornamenti dell'interfaccia utente di Lync 2013

<div>

## <a name="accessibility-updates"></a>Aggiornamenti per l'accessibilità

Lync 2013 include diverse nuove funzionalità di accessibilità.

  - Lync 2013 supporta la risoluzione a DPI elevata, consentendo agli utenti di scalare testo e grafica per 125% e 150% punti per pollice.

  - Lync offre un supporto a contrasto elevato in modo che l'interfaccia utente rimanga completamente funzionante quando viene usata con temi a contrasto elevato in Windows.

  - Lync offre più di 100 tasti di scelta rapida in modo che gli utenti possano accedere a funzioni importanti senza mouse. Ad esempio, gli utenti possono premere ALT + C per accettare una chiamata oppure ALT + I per ignorarla, senza dover TAB o impostare lo stato di attivazione. Premendo (ALT + Q) termina una chiamata, (CTRL + N) avvia OneNote e (Alt + T) apre il menu strumenti.

  - L'ampio supporto per la lettura dello schermo in Lync 2013 assicura che tutte le notifiche, le richieste in arrivo e i messaggi istantanei vengano lette ad alta voce quando è abilitata un'utilità per la lettura

</div>

<div>

## <a name="presence-while-sharing"></a>Presenza durante la condivisione

Quando Lync rileva che un utente sta condividendo, Lync assegna automaticamente all'utente uno stato presenza. Questo stato blocca tutte le comunicazioni in arrivo, a meno che al mittente non sia assegnata la relazione di privacy del gruppo di lavoro. Se l'utente usa la funzionalità di condivisione interamente su un monitor secondario, Lync non assegna uno stato presenza di presentazione.

</div>

<div>

## <a name="conversation-window-updates"></a>Aggiornamenti della finestra di conversazione

La finestra di conversazione riprogettata consente di accedere più rapidamente alle caratteristiche importanti.

  - Con la nuova funzionalità delle conversazioni a schede, gli utenti possono ora conservare tutti i loro messaggi istantanei e le chat room in una sola finestra di conversazione. Le schede lungo il lato sinistro della finestra di conversazione consentono agli utenti di spostarsi facilmente tra tutte le conversazioni attive.

  - Gli utenti possono estrarre una singola conversazione in una finestra separata e quindi ridimensionare la finestra. Possono anche riportare la finestra nella finestra principale della conversazione.

  - Lync 2013 riapre le conversazioni di un utente quando l'utente si disconnette e torna a Lync.

  - Gli utenti possono aggiungere rapidamente messaggi istantanei, video, condivisione di programmi, condivisione desktop o strumenti di conferenza Web (lavagna, note riunione, blocchi appunti condivisi e allegati) a qualsiasi conversazione.

  - In una riunione in cui viene condiviso il video o il contenuto, gli utenti possono visualizzare il video della riunione o il contenuto condiviso, quindi ridimensionare la finestra.

</div>

<div>

## <a name="lync-main-window-updates"></a>Aggiornamenti della finestra principale di Lync

Il nuovo aspetto semplificato mantiene le caratteristiche familiari, ad esempio **quello che succede oggi?** campo Nota, il selettore di stato e il selettore della **posizione** .

  - Quando sono abilitate le chat room, gli utenti vedranno una nuova icona **chat room** nella pagina principale di Lync. Con l'icona **chat room** , gli utenti possono accedere rapidamente alle chat room e ai filtri.

  - Gli utenti possono fare clic sulle icone della visualizzazione per passare alla visualizzazione **contatti** , alla visualizzazione **chat room** , alla visualizzazione **conversazioni** o alla visualizzazione **telefono** .

  - Se gli utenti hanno eseguito la migrazione a Exchange 2013, possono caricare un'immagine ad alta risoluzione.

</div>

<div>

## <a name="contacts-view-and-contact-card-updates"></a>Visualizzazione contatti e aggiornamenti della scheda contatto

Lync 2013 offre agli utenti diversi modi per visualizzare i contatti e i gruppi nella visualizzazione **contatti** .

  - Con il nuovo archivio contatti unificato, dopo la migrazione dei contatti Lync degli utenti a Exchange 2013, gli utenti possono accedere ai propri contatti e gestirli da Lync 2013, Outlook o Outlook Web App e i loro preferiti rimarranno sincronizzati. Ad esempio, se un utente aggiunge un contatto ai Preferiti in Outlook, il contatto viene visualizzato nel gruppo Preferiti in Lync 2013.

  - Se sono stati aggiunti e configurati il proxy XMPP e il gateway XMPP, gli utenti possono aggiungere contatti da partner basati su XMPP per la messaggistica istantanea e la presenza.

  - Un nuovo **Add a contact che non è presente nella funzionalità organizzazione** offre agli utenti un modo semplice per aggiungere persone esterne all'organizzazione.

  - Un nuovo gruppo di **Preferiti** consente agli utenti di creare un elenco di utenti contatti più spesso per velocizzare l'accesso.

  - Gli utenti possono usare la nuova pagina Opzioni **elenco contatti** per scegliere in che modo gli utenti vogliono ordinare e visualizzare i contatti. Gli utenti possono selezionare una visualizzazione espansa a due righe che mostra le immagini dei contatti o una visualizzazione a una riga ridotta. Gli utenti possono anche ordinare i contatti in ordine alfabetico o in base alla disponibilità.

</div>

<div>

## <a name="conferencing-updates"></a>Aggiornamenti per le conferenze

Lync 2013 offre diversi miglioramenti alle funzionalità di conferenza.

  - A seconda del tipo di riunione, gli utenti possono ora disattivare il pubblico e consentire o bloccare la condivisione di video durante la pianificazione della riunione. Queste opzioni sono disponibili nella pagina delle **Opzioni della riunione** e sono consigliate per riunioni di grandi dimensioni con più di 20 partecipanti.

  - I controlli audio facili da usare nella sala riunioni consentono all'utente di controllare le opzioni audio, ad esempio mute, riattivazioni, modifica dispositivo e così via.

  - Quando si condividono programmi, gli utenti possono selezionare più programmi da condividere se è necessario usare più di un programma.

  - Gli utenti possono ora caricare presentazioni che contengono clip video caricando il file di PowerPoint e puntando il mouse sulla diapositiva per visualizzare i controlli video, ad esempio riproduzione, pausa e controlli audio.

  - Durante una riunione, gli utenti possono unire un'altra conversazione aperta alla riunione usando **Unisci questa chiamata nel** menu **altre opzioni** (..**.**).

  - Per visualizzare i nomi dei partecipanti, gli utenti possono posizionare il puntatore del mouse sul pulsante **Visualizza partecipanti** oppure fare clic su **Mostra elenco** partecipanti per ancorare il pannello alla riunione.

  - A seconda del tipo di riunione, gli utenti possono scegliere tra diverse visualizzazioni di contenuti e partecipanti.

  - Le registrazioni delle riunioni vengono salvate automaticamente in un formato che viene riprodotto in Windows Media Player (MP4). Gli utenti possono condividere facilmente il file con chiunque o usare la caratteristica **pubblica** in Gestione registrazioni per pubblicare la registrazione in un percorso condiviso.

  - OneNote consente di collaborare a una riunione con nuovi modi. Durante una riunione, gli utenti possono prendere appunti con OneNote per uso personale dopo la riunione oppure usare i blocchi appunti condivisi e modificare la collaborazione con i partecipanti alla riunione in tempo reale. Tutti i membri del team possono accedere alle note condivise per fornire informazioni, idee Brainstorm o usare le pagine del blocco appunti come lavagna virtuale. Le persone e il contenuto condiviso nella riunione vengono aggiunti automaticamente alle note.

  - Gli utenti possono spostarsi tra i tipi di contenuto usando **Condividi contenuto e conduci attività di riunione** nella parte inferiore della sala riunioni. Gli utenti possono anche usare il menu **Gestisci contenuto presentabile** per scegliere il contenuto che si vuole condividere.

</div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Pianificazione per i client in Lync Server 2013](lync-server-2013-planning-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

