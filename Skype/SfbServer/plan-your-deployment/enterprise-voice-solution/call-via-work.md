---
title: Pianificare la chiamata tramite lavoro in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a33ec637-9ac8-4cb7-b3b2-88d432efc078
description: Pianificazione di Call Via Work in Skype for Business Server, che consente l'integrazione tra Skype for Business e il sistema telefonico PBX, in modo che gli utenti possano usare Skype for Business per controllare i telefoni PBX.
ms.openlocfilehash: 287f549d0b416e432eea771c07a7331e38a0b594
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58592530"
---
# <a name="plan-for-call-via-work-in-skype-for-business-server"></a>Pianificare la chiamata tramite lavoro in Skype for Business Server
 
Pianificazione di Call Via Work in Skype for Business Server, che consente l'integrazione tra Skype for Business e il sistema telefonico PBX, in modo che gli utenti possano usare Skype for Business per controllare i telefoni PBX.
  
 **Call Via Work** è una nuova funzionalità di Skype for Business Server che consente di integrare la soluzione Skype for Business con i sistemi telefonici PBX esistenti. Un utente abilitato per Chiama tramite lavoro può fare clic Skype for Business per chiamare un altro utente, all'interno della distribuzione o un utente esterno. La chiamata viene completata utilizzando il telefono PBX dell'utente. In questo modo un utente con un telefono PBX può includere l'audio nelle Skype for Business conversazioni. Nelle versioni precedenti del controllo delle chiamate remote di Lync Server era una funzionalità che consente agli utenti di controllare i telefoni PBX con Lync Server. In Skype for Business Server, questa funzionalità è stata sostituita con Chiama tramite lavoro.
  
Call Via Work abilita quanto segue per gli utenti di telefoni PBX
  
- Esperienza di chiamata a clic, con l'audio fornito tramite il telefono PBX.
    
- Presenza, ricerca utente e integrazione della messaggistica istantanea, ad esempio, due utenti chiamata tramite lavoro in una sessione di messaggistica istantanea possono aggiungere audio alla sessione, con l'audio fornito tramite i telefoni PBX.
    
- Possibilità di aggiungere messaggistica istantanea, condivisione applicazioni e trasferimento di file a una chiamata call via work.
    
- Funzionalità di partecipazione alle riunioni con un solo clic
    
## <a name="how-it-works"></a>Come funziona

Call Via Work utilizza Unified Communications Web API (UCWA) come agente utente back-to-back (B2BUA) tra il sistema PBX e la distribuzione di Skype for Business Server, in modo che non sia necessario alcun gateway CSTA (Computer-Supported Telecommunications Application) per connettersi Skype for Business Server con il sistema PBX. UCWA è un servizio introdotto nelle versioni precedenti di Lync Server per abilitare la connettività con client mobili e Web e viene installato automaticamente in ogni Front End Server.
  
### <a name="call-workflow-for-a-call-via-work-call"></a>Flusso di lavoro delle chiamate per una chiamata tramite lavoro

Di seguito viene illustrato in che modo un utente abilitato per La chiamata tramite lavoro può utilizzare il Skype for Business Server per effettuare una chiamata:
  
![Mostra i passaggi durante una chiamata call via work; prima il chiamante fa clic per chiamare qualcuno nel client Skype for Business; quindi UCWA squilla il telefono del chiamante. Quando il chiamante riprende il telefono, viene chiamato il destinatario](../../media/050e88ed-e18e-40c0-84d5-b17fe40c305a.jpg)
  
1. L'utente seleziona un utente nel Skype for Business client e fa clic sull'icona del telefono per chiamarlo. In caso contrario, durante una conversazione di messaggistica istantanea, l'utente fa clic per chiamare l'utente con cui sta avendo la sessione.
    
2. Il telefono PBX dell'utente che ha effettuato la chiamata inizia a squillare. L'ID chiamante per questo telefono mostra un numero di telefono globale configurato per essere visualizzato nell'ID chiamante di tutti gli utenti che effettuano chiamate di chiamata tramite ufficio. Questo numero di telefono globale non è un numero di telefono effettivo corrispondente al telefono di una persona. Si tratta invece di un segnale visivo che consente all'utente di sapere che si tratta della propria chiamata in uscita e non di una chiamata in arrivo che avviene contemporaneamente. Quando si distribuisce Chiama tramite ufficio, è consigliabile informare gli utenti su questo numero di telefono globale e sul suo significato.
    
3. L'utente che ha effettuato la chiamata preleva il telefono PBX. Skype for Business quindi avvia la chiamata vocale al chiamato. 
    
4. Quando il chiamato risponde, inizia la chiamata vocale. Se i due utenti hanno già avuto una sessione di messaggistica istantanea in corso, è possibile continuare.
    
### <a name="joining-a-conference-with-call-via-work"></a>Partecipare a una conferenza con chiamata tramite lavoro

Un utente chiamata tramite lavoro può partecipare a una riunione pianificata facendo clic sull'URL della riunione. Skype for Business viene quindi visualizzato un messaggio Di chiamata in uscita **fino** a quando il servizio riunione non compone il telefono PBX dell'utente. L'utente Chiama tramite ufficio prende quindi il telefono PBX e partecipa alla riunione.
  
Un utente chiamata tramite lavoro  può anche usare l'opzione Riunione Skype for Business per creare riunioni Riunione ora. L'utente visualizza quindi il messaggio Chiamata **in** uscita e il telefono PBX squilla.
  
Un utente di Call Via Work può anche effettuare l'accesso a una riunione chiamando il numero del ponte per conferenze dall'interno di Skype for Business. Se è necessario un PIN di conferenza, l'utente deve usare il telefono PBX per immettere il PIN.
  
### <a name="incoming-calls"></a>Chiamate in arrivo

Quando un utente abilitato per Call Via Work riceve una chiamata Skype for Business, il telefono PBX e i client Skype for Business dell'utente squillano contemporaneamente (se l'utente ha configurato l'anello simultaneo). L'utente può accettare la chiamata raccogliendo  il telefono PBX o facendo clic su Accetta nella Skype for Business notifica. Se l'utente accetta la chiamata utilizzando Skype for Business, la finestra Skype for Business per la chiamata rimane aperta. Tuttavia, se l'utente accetta la chiamata raccogliendo il telefono PBX, la finestra di notifica di Skype for Business si chiude e non esiste una sessione Skype for Business, solo la chiamata vocale tramite il telefono PBX.
  
Quando un utente abilitato per La chiamata tramite ufficio riceve una chiamata PBX, squilla solo il telefono PBX.
  
## <a name="limitations-of-call-via-work"></a>Limitazioni della chiamata tramite lavoro

Call Via Work è una soluzione vocale che richiede poca configurazione hardware, ma presenta limitazioni rispetto alle funzionalità disponibili in modalità VoIP aziendale o controllo delle chiamate remote. Call Via Work presenta le limitazioni seguenti:
  
- Se un utente chiama tramite ufficio ha configurato l'inoltro di chiamata al numero di richiamata Chiama tramite ufficio e qualcuno tenta di invitare l'utente a una riunione tramite il numero di telefono dell'utente, l'invito non raggiungerà l'utente. È consigliabile informare gli utenti di invitare i partecipanti alle riunioni facendo clic sul nome e non sul numero di telefono. 
    
- La funzionalità avanzata 911 e l'analisi delle chiamate dannose non sono disponibili durante le chiamate call via work.
    
- Gli utenti abilitati per La chiamata tramite lavoro non possono utilizzare le funzionalità di delega, chiamata del team o Response Group.
    
- Gli utenti di Call Via Work non possono utilizzare Skype for Business per registrare una riunione, disattivare o riattivare l'audio della chiamata, tenere o trasferire la chiamata o utilizzare il parcheggio di chiamata.
    
- Gli utenti non possono utilizzare Call Via Work per accedere ai messaggi della segreteria telefonica PBX.
    
- Gli utenti di Call Via Work non possono inoltrare una sessione avviata come chiamata vocale a una riunione di collaborazione che include comunicazioni quali video, Powerpoint, lavagna o One Note.
    
- Gli utenti di Call Via Work non possono aggiungere altri utenti a una chiamata di due persone.
    
- Nessun supporto per l'associazione di deskphone o l'associazione di plug-in VDI.
    
- Se un utente effettua o risponde a una chiamata utilizzando il telefono PBX (e non utilizzando la finestra Skype for Business), non verrà visualizzato alcun registro della chiamata.
    
- Se il sistema PBX non supporta **IL RIFERIMENTO con le sostituzioni,** si verifica il comportamento seguente. Durante una chiamata di chiamata tramite lavoro, se l'utente trasferisce la chiamata in corso dal sistema PBX Telefono, la finestra della chiamata non scomparirà dalla finestra Skype for Business chiamata. Se l'utente chiude la finestra di chiamata, la chiamata tra l'obiettivo di trasferimento e il destinatario del trasferimento terminerà. 
    
## <a name="prerequisites-for-call-via-work"></a>Prerequisiti per la chiamata tramite lavoro

Per abilitare tutti gli utenti per La chiamata tramite lavoro, è necessario disporre di alcuni prerequisiti. Per ulteriori informazioni su questi prerequisiti e per la procedura per abilitare gli utenti per La chiamata tramite lavoro, vedere [Deploy Call Via Work in Skype for Business Server 2015.](../../deploy/deploy-call-via-work.md) 
  
## <a name="see-also"></a>Vedere anche

[Pianificare il controllo delle chiamate remote in Skype for Business](remote-call-control.md)
  
[Distribuire chiamata tramite lavoro in Skype for Business Server 2015](../../deploy/deploy-call-via-work.md)

