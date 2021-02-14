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
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a33ec637-9ac8-4cb7-b3b2-88d432efc078
description: Pianificazione della chiamata tramite ufficio in Skype for Business Server, che consente l'integrazione tra Skype for Business e il sistema telefonico PBX, in modo che gli utenti possano usare Skype for Business per controllare i loro telefoni PBX.
ms.openlocfilehash: e443a5d2709f1aca69ef200e72de43251cd16047
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825876"
---
# <a name="plan-for-call-via-work-in-skype-for-business-server"></a>Pianificare la chiamata tramite lavoro in Skype for Business Server
 
Pianificazione della chiamata tramite ufficio in Skype for Business Server, che consente l'integrazione tra Skype for Business e il sistema telefonico PBX, in modo che gli utenti possano usare Skype for Business per controllare i loro telefoni PBX.
  
 **Chiamata tramite ufficio** è una nuova funzionalità di Skype for Business Server che consente di integrare la soluzione Skype for Business con i sistemi telefonici PBX esistenti. Un utente abilitato per La chiamata tramite lavoro può fare clic in Skype for Business per chiamare un altro utente, all'interno della distribuzione o un utente esterno. La chiamata viene completata utilizzando il telefono PBX dell'utente. Ciò consente a un utente con un telefono PBX di includere l'audio nelle conversazioni di Skype for Business. Nelle versioni precedenti del controllo delle chiamate remote di Lync Server era disponibile una funzionalità che consente agli utenti di controllare i telefoni PBX con Lync Server. In Skype for Business Server, questa funzionalità è stata sostituita con Chiama da lavoro.
  
Chiamata tramite ufficio consente agli utenti di telefoni PBX di eseguire le operazioni seguenti
  
- Esperienza di chiamata a clic, con l'audio fornito tramite il telefono PBX.
    
- Presenza, ricerca degli utenti e integrazione della messaggistica istantanea. Ad esempio, due utenti chiamata tramite lavoro in una sessione di messaggistica istantanea possono aggiungere audio alla sessione, con l'audio fornito tramite i telefoni PBX.
    
- Possibilità di aggiungere messaggistica istantanea, condivisione applicazioni e trasferimento di file a una chiamata chiamata tramite lavoro.
    
- Funzionalità di partecipazione alle riunioni con un solo clic
    
## <a name="how-it-works"></a>Funzionamento

Call Via Work usa Unified Communications Web API (UCWA) come agente utente back-to-back (B2BUA) tra il sistema PBX e la distribuzione di Skype for Business Server, in modo che non sia necessario alcun gateway CSTA (Computer-Supported Telecommunications Application) per connettere Skype for Business Server al sistema PBX. UCWA è un servizio introdotto nelle versioni precedenti di Lync Server per abilitare la connettività con client mobili e Web e viene installato automaticamente in ogni Front End Server.
  
### <a name="call-workflow-for-a-call-via-work-call"></a>Flusso di lavoro di chiamata per una chiamata di tipo Chiamata tramite lavoro

Di seguito viene illustrato come un utente abilitato per La chiamata tramite lavoro può usare Skype for Business Server per effettuare una chiamata:
  
![Mostra i passaggi durante una chiamata call via work; prima il chiamante fa clic per chiamare qualcuno nel client Skype for Business; quindi UCWA squilla il telefono del chiamante. Quando il chiamante riprende il telefono, viene chiamato il destinatario](../../media/050e88ed-e18e-40c0-84d5-b17fe40c305a.jpg)
  
1. L'utente seleziona un utente nel client Skype for Business e fa clic sull'icona del telefono per chiamarlo. Oppure, durante una conversazione di messaggistica istantanea, l'utente fa clic per chiamare l'utente con cui sta avendo la sessione.
    
2. Il telefono PBX dell'utente che ha effettuato la chiamata inizia a squillare. L'ID chiamante per questo telefono mostra un numero di telefono globale che è stato configurato per essere visualizzato nell'ID chiamante di tutti gli utenti che effettuano chiamate Call Via Work. Questo numero di telefono globale non è un numero di telefono effettivo corrispondente al telefono di una persona. Si tratta invece di un segnale visivo per far sapere all'utente che si tratta di una propria chiamata in uscita e non di una chiamata in arrivo che avviene contemporaneamente. Quando si distribuisce La chiamata tramite ufficio, è consigliabile informare gli utenti su questo numero di telefono globale e sul suo significato.
    
3. L'utente che ha effettuato la chiamata preleva il telefono PBX. Skype for Business avvia quindi la chiamata vocale al chiamato. 
    
4. Quando il chiamato risponde, inizia la chiamata vocale. Se i due utenti hanno già avuto una sessione di messaggistica istantanea in corso, è possibile continuare.
    
### <a name="joining-a-conference-with-call-via-work"></a>Partecipare a una conferenza con chiamata tramite lavoro

Un utente Chiamata tramite lavoro può partecipare a una riunione pianificata facendo clic sull'URL della riunione. Skype for Business mostra quindi un **messaggio** di chiamata in uscita fino a quando il servizio riunione non compone il telefono PBX dell'utente. L'utente Chiama tramite ufficio prende quindi il telefono PBX e partecipa alla riunione.
  
Un utente chiamata tramite l'azienda può anche usare **l'opzione Riunione** ora in Skype for Business per creare riunioni Riunione ora. L'utente visualizza quindi la chiamata **in uscita al** messaggio e il telefono PBX squilla.
  
Un utente chiamata tramite l'azienda può anche accedere a una riunione chiamando il numero del bridge di conferenza da Skype for Business. Se è necessario un PIN di conferenza, l'utente deve utilizzare il telefono PBX per immettere il PIN.
  
### <a name="incoming-calls"></a>Chiamate in arrivo

Quando un utente abilitato per La chiamata tramite ufficio riceve una chiamata Skype for Business, il telefono PBX e i client Skype for Business dell'utente squillano tutti contemporaneamente (se l'utente ha configurato lo squillo simultaneo). L'utente può accettare la chiamata selezionando il telefono PBX o facendo clic su **Accetta** nella notifica di Skype for Business. Se l'utente accetta la chiamata tramite Skype for Business, la finestra di Skype for Business per la chiamata rimane aperta. Ma se l'utente accetta la chiamata riprendendo il telefono PBX, la finestra di notifica di Skype for Business si chiude e non c'è alcuna sessione di Skype for Business, solo la chiamata vocale sul telefono PBX.
  
Quando un utente abilitato per La chiamata tramite ufficio riceve una chiamata PBX, squilla solo il telefono PBX.
  
## <a name="limitations-of-call-via-work"></a>Limitazioni della chiamata tramite lavoro

Chiamata tramite lavoro è una soluzione vocale che richiede poche configurazioni hardware, ma presenta limitazioni rispetto alle funzionalità disponibili in modalità VoIP aziendale controllo delle chiamate remote. La chiamata tramite lavoro presenta le limitazioni seguenti:
  
- Se un utente chiamata tramite ufficio ha configurato l'inoltro di chiamata al numero di richiamata Chiamata tramite ufficio e qualcuno tenta di invitare l'utente a una riunione tramite il numero di telefono dell'utente, l'invito non raggiungerà l'utente. È consigliabile informare gli utenti di invitare i partecipanti alle riunioni facendo clic sul nome e non sul numero di telefono. 
    
- La funzionalità enhanced 911 e l'analisi delle chiamate dannose non sono disponibili durante le chiamate Call Via Work.
    
- Gli utenti abilitati per La chiamata tramite lavoro non possono utilizzare le funzionalità di delega, chiamata al team o Response Group.
    
- Gli utenti di Call Via Work non possono usare Skype for Business per registrare una riunione, disattivare o riattivare l'audio della chiamata, tenere o trasferire la chiamata o usare il parcheggio di chiamata.
    
- Gli utenti non possono utilizzare Chiama da lavoro per accedere ai messaggi della segreteria telefonica PBX.
    
- Gli utenti di Chiamata tramite lavoro non possono inoltrare una sessione avviata come chiamata vocale a una riunione di collaborazione che include comunicazioni quali video, Powerpoint, lavagna o Una nota.
    
- Gli utenti di Chiamata tramite lavoro non possono aggiungere altri utenti a una chiamata di due persone.
    
- Nessun supporto per l'associazione del telefono da tavolo o l'associazione del plug-in VDI.
    
- Se un utente effettua o risponde a una chiamata utilizzando il telefono PBX (e non utilizzando la finestra di Skype for Business), non ci sarà alcun registro della chiamata.
    
- Se il sistema PBX non supporta **REFER con Replaces,** si verifica il comportamento seguente. Durante una chiamata di chiamata tramite ufficio, se l'utente trasferisce la chiamata in corso dal telefono PBX, la finestra della chiamata non scomparirà dalla finestra di Skype for Business. Se l'utente chiude la finestra di chiamata, la chiamata tra l'obiettivo di trasferimento e il destinatario del trasferimento terminerà. 
    
## <a name="prerequisites-for-call-via-work"></a>Prerequisiti per la chiamata tramite lavoro

Per abilitare gli utenti alla funzionalità Chiama da lavoro, è necessario disporre di alcuni prerequisiti. Per ulteriori informazioni su questi prerequisiti e per istruzioni su come abilitare gli utenti per La chiamata tramite il lavoro, vedere Distribuire chiamate tramite lavoro [in Skype for Business Server 2015.](../../deploy/deploy-call-via-work.md) 
  
## <a name="see-also"></a>Vedere anche

[Pianificare il controllo delle chiamate remote in Skype for Business](remote-call-control.md)
  
[Distribuire chiamate tramite lavoro in Skype for Business Server](../../deploy/deploy-call-via-work.md)

