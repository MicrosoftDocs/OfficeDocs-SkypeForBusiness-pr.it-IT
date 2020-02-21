---
title: 'Lync Server 2013: novità per i client'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: What's new for clients
ms:assetid: 5c144677-4d58-4fc3-8445-74b76c9fcf07
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204933(v=OCS.15)
ms:contentKeyID: 48184253
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc8ea4abd3608863dea1bf914f5d89cc0ad43fae
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210973"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="whats-new-for-clients-in-lync-server-2013"></a>Novità per i client in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-19_

Microsoft Lync 2013 dispone di un'interfaccia utente riprogettata e di nuove importanti caratteristiche. Per gli amministratori, il client è ora incluso nel programma di installazione di Office, offrendo un approccio più semplificato alla distribuzione di Office e alla personalizzazione dei client nell'organizzazione.

<div>


> [!NOTE]  
> Per una visualizzazione illustrata degli aggiornamenti dell'interfaccia utente di Lync 2013, vedere "What ' s New in <A href="https://go.microsoft.com/fwlink/?linkid=273885">https://go.microsoft.com/fwlink/?LinkId=273885</A>Lync 2013" at.



</div>

<div>

## <a name="integration-with-office-setup"></a>Integrazione con l'installazione di Office

Il client Lync 2013 e il componente aggiuntivo per riunioni online per Lync 2013, che supporta la gestione delle riunioni dall'interno del client di messaggistica e collaborazione di Outlook, sono ora entrambi inclusi nel programma di installazione di Office 2013.

Nelle versioni precedenti di Lync e Office Communicator, è possibile utilizzare le proprietà di Windows Installer per personalizzare e controllare l'installazione di Office. Poiché Lync 2013 è integrato con l'installazione di Office, è possibile utilizzare i metodi seguenti per personalizzare il programma di installazione di Lync 2013:

  - Utilizzare lo Strumento di personalizzazione di Office

  - Utilizzare il file Config.xml per eseguire le attività di installazione

  - Utilizzare le opzioni della riga di comando del programma di installazione

<div>


> [!NOTE]  
> Il programma di installazione di Lync 2013 non disinstalla le versioni precedenti di Lync o Office Communicator. Il client Lync 2013 installa affiancati con altri client Lync o Office Communicator



</div>

Per informazioni dettagliate, vedere [Deploying Lync Clients in Lync Server 2013](lync-server-2013-deploying-lync-clients.md).

</div>

<div>

## <a name="group-policy-deployment"></a>Distribuzione di Criteri di gruppo

Poiché Lync 2013 è ora incluso nel programma di installazione di Office, il metodo per la distribuzione delle impostazioni di criteri di gruppo di Lync è stato modificato. Nelle versioni precedenti di Lync e Office Communicator, è possibile utilizzare il file Communicator. adm per definire le impostazioni di criteri di gruppo, mentre in Lync 2013 è ora consentito utilizzare i modelli amministrativi ADMX e ADML di Lync forniti insieme ai criteri di gruppo di Office Modelli amministrativi.

Per ulteriori informazioni, vedere [impostazioni di criteri di gruppo per Lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md).

</div>

<div>

## <a name="outlook-scheduling-add-in-updates"></a>Aggiornamenti del componente aggiuntivo di Outlook per la pianificazione delle riunioni

Il componente aggiuntivo per riunioni online per Lync 2013 include la personalizzazione dell'invito alla riunione e le nuove opzioni di riunione.

  - Gli amministratori possono personalizzare gli inviti alle riunioni dell'organizzazione aggiungendo un logo personalizzato, un URL di supporto, un URL per la dichiarazione di non responsabilità legale o un testo personalizzato per il piè di pagina. Per ulteriori informazioni, vedere [personalizzazione del componente aggiuntivo per riunioni online in Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md).

  - I nuovi controlli per la disattivazione dell'audio dei partecipanti consentono agli organizzatori delle riunioni di disattivare l'audio e il video dei partecipanti per impostazione predefinita.

</div>

<div>

## <a name="virtual-desktop-infrastructure-plug-in"></a>Plug-in VDI (Virtual Desktop Infrastructure)

Il client Lync 2013 supporta ora l'audio e il video in un ambiente VDI (Virtual Desktop Infrastructure). Un utente può connettere un dispositivo audio o video (ad esempio un auricolare o una videocamera) al computer locale (ad esempio un thin client o un computer ricondizionato). L'utente può connettersi alla macchina virtuale, accedere al client Lync 2013 in esecuzione nella macchina virtuale e partecipare alla comunicazione audio e video in tempo reale come se il client è in esecuzione localmente. In un ambiente desktop virtuale sono supportate le funzionalità seguenti:

  - Integrazione dei dispositivi per audio e video, incluso quanto segue:
    
      - Controlli di chiamata dal dispositivo
    
      - Integrazione della presenza nel dispositivo
    
      - Supporto di più HID (Human Interface Device)

  - Supporto di servizi di geolocalizzazione ed emergenza.

  - Supporto per tutte le modalità di Lync, tra cui messaggistica istantanea, audio, video, condivisione applicazioni, condivisione del desktop, condivisione di PowerPoint, lavagna e trasferimento di file.

  - Supporto di audio e video nelle chiamate e nelle conferenze telefoniche a due.

Per informazioni sulla distribuzione del plug-in VDI, vedere [Deploying the Lync VDI plug-in in Lync Server 2013](lync-server-2013-deploying-the-lync-vdi-plug-in.md).

</div>

<div>

## <a name="video-enhancements"></a>Miglioramenti relativi alle funzionalità video

Molte nuove funzionalità migliorano in modo sostanziale l'esperienza video per i partecipanti alle conferenze.

  - Le funzionalità video sono ottimizzate con rilevamento dei volti e framing intelligente, in modo che il video del partecipante si sposti automaticamente in modo che il volto rimanga centrato nel fotogramma.

  - È ora supportato il video ad alta definizione per le chiamate a due e le conferenze con più partecipanti. Gli utenti potranno usufruire di risoluzioni fino a 1080p HD.

  - I partecipanti possono scegliere tra diversi layout per le riunioni. Con la visualizzazione Raccolta vengono visualizzati i video o le immagini di tutti i partecipanti. Nella visualizzazione relatore viene mostrato il contenuto della riunione e solo il video o l'immagine del relatore corrente. La visualizzazione presentazione mostra solo il contenuto della riunione e la visualizzazione compatta include solo i controlli per la riunione.

  - Con la nuova funzionalità Raccolta, i partecipanti possono visualizzare più feed video contemporaneamente. Se alla conferenza partecipano più di cinque persone, nella prima riga saranno visualizzati solo i feed video dei partecipanti più attivi, mentre per gli altri partecipanti verranno visualizzate le immagini.

  - I partecipanti possono scegliere di bloccare il video per selezionare uno o più feed video tra quelli disponibili, in modo che siano sempre visibili.

  - I relatori possono utilizzare la funzionalità di video in evidenza per selezionare il feed video di una persona in modo che tutti gli altri partecipanti alla riunione vedano solo il video di tale partecipante.

</div>

<div>

## <a name="chat-room-integration"></a>Integrazione delle chat room

Lync 2013 ora integra le funzionalità precedentemente fornite da Lync 2010 Group Chat. Non è più necessario un client Group Chat separato.

  - Dall'interno di Lync 2013, gli utenti possono cercare chat room, aggiungere chat room ai propri contatti, monitorare l'attività della chat e leggere e inviare messaggi.

  - Gli utenti possono creare feed di argomenti in modo da ricevere notifica nel caso qualcuno nelle chat room seguite aggiunga un post con parole chiave specifiche.

  - Con la nuova pagina di opzioni **Chat persistente** gli utenti possono impostare avvisi e suoni di notifica applicabili al post di messaggi nelle loro chat room.

</div>

<div>

## <a name="lync-web-app-updates"></a>Aggiornamenti di Lync Web App

Lync Web App è il client di conferenza basato sul Web per le riunioni di Lync Server 2013. In questa versione l'aggiunta di audio e video per computer a Lync Web App offre un'esperienza di riunione completa per tutti gli utenti che non dispongono di un client Lync installato localmente. I partecipanti alla riunione hanno accesso a tutte le funzionalità di collaborazione e condivisione, oltre ai controlli della riunione per il relatore.

Quando un utente tenta di partecipare a una riunione ma non dispone di un client installato localmente, viene aperto Lync Web App. Se si desidera consentire ulteriori opzioni per l'adesione alla riunione, è possibile configurare la pagina di partecipazione alla riunione; vedere [Configuring the meeting join page in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) nella documentazione relativa alla distribuzione.

A causa dei miglioramenti apportati a Lync Web App, una versione aggiornata di Attendee non è disponibile per Lync Server 2013. Lync Web App è il client preferito per i partecipanti all'esterno dell'organizzazione. Non è richiesta l'installazione di un client locale, anche se per le funzionalità audio, video e di condivisione è necessario installare un plug-in al primo utilizzo.

</div>

<div>

## <a name="lync-2013-for-mobile-clients-updates"></a>Lync 2013 per gli aggiornamenti dei client mobili

Oltre alla presenza avanzata, ai contatti e alle funzionalità di messaggistica istantanea, i client per dispositivi mobili Lync 2013 ora offrono chiamate vocali e video su Internet e sulle connessioni dati telefoniche. Con un singolo tocco del collegamento alla riunione in un elemento del calendario, gli utenti di dispositivi mobili possono partecipare alle riunioni video e vocali di Lync. Per ulteriori informazioni sui client di Lync 2013 per dispositivi mobili, vedere [Planning for Mobile Clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).

</div>

<div>

## <a name="lync-2013-user-interface-updates"></a>Aggiornamenti dell'interfaccia utente di Lync 2013

<div>

## <a name="accessibility-updates"></a>Aggiornamenti dell'accessibilità

Lync 2013 include diverse nuove funzionalità di accessibilità.

  - Lync 2013 supporta la risoluzione ad alto DPI, consentendo agli utenti di scalare il testo e la grafica per il 125% e 150% punti per pollice.

  - Lync fornisce un supporto a contrasto elevato, in modo che l'interfaccia utente rimanga completamente funzionante quando viene utilizzata con temi con contrasto elevato in Windows.

  - Lync offre più di 100 tasti di scelta rapida in modo che gli utenti possano accedere a funzioni importanti senza un mouse. È ad esempio possibile premere ALT+C per accettare una chiamata o ALT+I per ignorarla, senza doversi spostare con TAB o impostare lo stato attivo. Premendo ALT+Q si interrompe una chiamata, con CTRL+N si avvia OneNote e ALT+T consente di aprire il menu Strumenti.

  - Il supporto per i lettori di schermo estensivo in Lync 2013 garantisce che tutte le notifiche, le richieste in arrivo e i messaggi istantanei vengano lette ad alta voce quando è abilitato un lettore schermo.

</div>

<div>

## <a name="presence-while-sharing"></a>Stato presenza durante la condivisione

Quando Lync rileva che un utente sta condividendo, Lync assegna automaticamente all'utente lo stato di presenza di una presentazione. Questo stato blocca tutte le comunicazioni in arrivo, a meno che al mittente non sia assegnata la relazione di privacy Gruppo di lavoro. Se l'utente utilizza la funzionalità di condivisione interamente su un monitor secondario, Lync non assegna uno stato di presenza di presentazione.

</div>

<div>

## <a name="conversation-window-updates"></a>Aggiornamenti della finestra di conversazione

La finestra di conversazione riprogettata consente di accedere più rapidamente a funzionalità importanti.

  - Con la nuova funzionalità per le conversazioni su schede, gli utenti possono ora mantenere tutti i messaggi istantanei e le chat room in una singola finestra di conversazione. Le schede lungo il lato sinistro di questa finestra consentono agli utenti di spostarsi facilmente tra tutte le conversazioni attive.

  - Gli utenti possono disancorare una singola conversazione visualizzandola in una finestra separata e poi ridimensionare la finestra. È inoltre possibile riancorare la finestra alla finestra di conversazione principale.

  - Lync 2013 consente di riaprire le conversazioni di un utente quando l'utente esegue l'accesso e la firma di nuovo in Lync.

  - Gli utenti possono aggiungere rapidamente gli strumenti per messaggi istantanei, video, condivisione dei programmi, condivisione del desktop o conferenze Web (lavagna, note delle riunioni, blocchi appunti condivisi e allegati) a qualsiasi conversazione.

  - In una riunione con video o contenuto condiviso, gli utenti possono disancorare il video o il contenuto condiviso della riunione e quindi ridimensionare la finestra.

</div>

<div>

## <a name="lync-main-window-updates"></a>Aggiornamenti della finestra principale di Lync

Il nuovo aspetto ottimizzato conserva caratteristiche familiari come il campo note **Cosa succede oggi**, il selettore di stato e il selettore **Imposta la posizione**.

  - Quando le chat room sono abilitate, gli utenti visualizzano una nuova icona delle **chat room** nella pagina principale di Lync. Con l'icona**Chat room** gli utenti possono accedere rapidamente a chat room e filtri.

  - È possibile fare clic sulle icone delle visualizzazioni per passare rapidamente alla visualizzazione **Contatti**, **Chat room**, **Conversazioni** o **Telefono**.

  - Se gli utenti sono stati migrati a Exchange 2013, è possibile caricare un'immagine ad alta risoluzione.

</div>

<div>

## <a name="contacts-view-and-contact-card-updates"></a>Aggiornamenti della visualizzazione Contatti e dei biglietti da visita

Lync 2013 offre agli utenti diversi modi per visualizzare i contatti e i gruppi nella visualizzazione **contatti** .

  - Con il nuovo archivio contatti unificato, dopo la migrazione dei contatti Lync degli utenti a Exchange 2013, gli utenti possono accedere e gestire i propri contatti da Lync 2013, Outlook o Outlook Web App e i loro preferiti rimangono sincronizzati. Ad esempio, se un utente aggiunge un contatto ai Preferiti in Outlook, il contatto viene visualizzato nel gruppo Preferiti in Lync 2013.

  - Se si aggiungono e configurano il proxy XMPP e il gateway XMPP, gli utenti possono aggiungere contatti dai partner XMPP per la messaggistica istantanea e la presenza.

  - La nuova funzionalità **Aggiungi contatto esterno all'organizzazione** consente di aggiungere facilmente persone esterne all'organizzazione.

  - Un nuovo gruppo **Preferiti** consente agli utenti di creare un elenco di persone contattate più di frequente per accedervi più rapidamente.

  - È possibile utilizzare la nuova pagina di opzioni **Elenco contatti** per scegliere la modalità di ordinamento e visualizzazione dei contatti. È possibile selezionare una visualizzazione espansa su due righe che include le immagini dei contatti oppure una visualizzazione ridotta su una riga. Gli utenti possono inoltre disporre i contatti in ordine alfabetico o di disponibilità.

</div>

<div>

## <a name="conferencing-updates"></a>Aggiornamenti per le conferenze

Lync 2013 offre numerosi miglioramenti alle funzionalità di conferenza.

  - A seconda del tipo di riunione, è ora possibile disattivare l'audio per il pubblico e consentire o impedire la condivisione del video in fase di pianificazione della riunione. Queste opzioni sono disponibili nella pagina **Opzioni riunione** ed è consigliabile utilizzarle per riunioni con più di 20 partecipanti.

  - I controlli audio di facile utilizzo nella sala riunioni consentono di controllare le opzioni per l'audio, ad esempio disattivare l'audio, riattivare l'audio, cambiare dispositivo e così via.

  - Per la condivisione dei programmi è ora possibile selezionare più programmi da condividere se si desidera utilizzare più di un programma.

  - È ora possibile caricare presentazioni che contengono clip video. È sufficiente caricare il file di PowerPoint e posizionare il mouse sulla diapositiva per visualizzare i controlli video, come i controlli di riproduzione e pausa, nonché i controlli audio.

  - Durante una riunione è possibile unire un'altra conversazione aperta scegliendo **Unisci la chiamata a** nel menu **Altre opzioni** (**…**).

  - Per visualizzare i nomi dei partecipanti, è possibile passare il mouse sul pulsante **Mostra partecipanti** oppure fare clic su **Mostra elenco partecipanti** per ancorare il pannello nella riunione.

  - A seconda del tipo di riunione, è possibile scegliere tra varie visualizzazioni diverse per contenuto e partecipanti.

  - Le registrazioni delle riunioni vengono salvate automaticamente in un formato riproducibile in Windows Media Player (MP4). È possibile condividere facilmente il file con chiunque oppure utilizzare la funzionalità **Pubblica** in Gestione registrazioni per pubblicare la registrazione in una posizione condivisa.

  - OneNote rende possibili nuovi scenari di collaborazione in una riunione. Durante una riunione è possibile aggiungere note con OneNote da utilizzare personalmente durante la riunione oppure utilizzare blocchi appunti condivisi per modificarli insieme agli altri partecipanti in tempo reale. Tutti i membri del team possono accedere alle note condivise per fornire il loro contributo, scambiarsi idee o utilizzare le pagine del blocco appunti come lavagna virtuale. Le persone e il contenuto condivisi nella riunione vengono aggiunti automaticamente alle note.

  - È possibile passare da un tipo di contenuto all'altro tramite **Condividi contenuto e conduci attività di riunione** nella parte inferiore della sala riunioni. È inoltre possibile utilizzare il menu **Gestisci contenuto presentabile** per scegliere il contenuto da condividere.

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

