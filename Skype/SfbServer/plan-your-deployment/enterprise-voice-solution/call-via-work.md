---
title: Pianificare la chiamata tramite il lavoro in Skype for Business Server
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
description: Pianificazione della chiamata tramite il lavoro in Skype for Business Server, che consente l'integrazione tra Skype for business e il sistema telefonico PBX, in modo che gli utenti possano usare Skype for business per controllare i telefoni PBX.
ms.openlocfilehash: e443a5d2709f1aca69ef200e72de43251cd16047
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825876"
---
# <a name="plan-for-call-via-work-in-skype-for-business-server"></a>Pianificare la chiamata tramite il lavoro in Skype for Business Server
 
Pianificazione della chiamata tramite il lavoro in Skype for Business Server, che consente l'integrazione tra Skype for business e il sistema telefonico PBX, in modo che gli utenti possano usare Skype for business per controllare i telefoni PBX.
  
 **Call by work** è una nuova funzionalità di Skype for Business Server che consente di integrare la soluzione Skype for business con i sistemi di telefonia PBX esistenti. Un utente abilitato per la chiamata tramite lavoro può fare clic su Skype for business per chiamare un altro utente, sia all'interno della distribuzione che di un utente esterno. La chiamata viene completata mediante il telefono PBX dell'utente. In questo modo un utente con un telefono PBX deve includere l'audio nelle conversazioni ricche di Skype for business. Nelle versioni precedenti del controllo delle chiamate remote di Lync Server era presente una funzionalità che consente agli utenti di controllare i telefoni PBX con Lync Server. In Skype for Business Server, questa funzionalità è stata sostituita da chiamata tramite lavoro.
  
Chiamata tramite lavoro consente di abilitare le seguenti operazioni per gli utenti di telefoni PBX
  
- Esperienza di chiamata a portata di clic, con l'audio fornito tramite il telefono PBX.
    
- La presenza, la ricerca dell'utente e l'integrazione di messaggistica istantanea, ad esempio due chiamate tramite utenti di lavoro in una sessione di messaggistica istantanea, possono aggiungere audio alla propria sessione, con l'audio fornito tramite i telefoni PBX.
    
- La possibilità di aggiungere la messaggistica istantanea, la condivisione di applicazioni e il trasferimento di file a una chiamata tramite la chiamata di lavoro.
    
- Funzionalità di partecipazione alle riunioni con un solo clic
    
## <a name="how-it-works"></a>Funzionamento

Chiamata tramite lavoro utilizza Unified Communications Web API (UCWA) come agente utente back-to-back (B2BUA) tra il sistema PBX e la distribuzione di Skype for Business Server, in modo che non sia necessario il gateway di applicazioni per le telecomunicazioni supportate da computer per connettere Skype for Business Server con il sistema PBX. UCWA è un servizio introdotto nelle versioni precedenti di Lync Server per abilitare la connettività con i client mobili e Web e viene installato automaticamente in tutti i Front End Server.
  
### <a name="call-workflow-for-a-call-via-work-call"></a>Flusso di lavoro di chiamata per una chiamata tramite chiamata

Di seguito viene illustrato come un utente abilitato per la chiamata tramite lavoro può utilizzare il server Skype for business per effettuare una chiamata:
  
![Visualizza la procedura durante una chiamata tramite la chiamata di lavoro. in primo luogo il chiamante fa clic per chiamare un utente nel client Skype for business; poi il UCWA squilla il telefono del chiamante. Quando il chiamante preleva il telefono, il destinatario viene chiamato](../../media/050e88ed-e18e-40c0-84d5-b17fe40c305a.jpg)
  
1. L'utente seleziona un utente nel client Skype for business e fa clic sull'icona del telefono per chiamarli. In alternativa, durante una conversazione di messaggistica istantanea, l'utente fa clic per chiamare l'utente con cui si sta effettuando la sessione.
    
2. Il telefono PBX dell'utente che ha effettuato la chiamata inizia a squillare. L'ID chiamante per questo telefono mostra un numero di telefono globale che è stato configurato per essere visualizzato nell'ID chiamante di tutti gli utenti che effettuano la chiamata tramite le chiamate di lavoro. Questo numero di telefono globale non corrisponde a un numero di telefono effettivo corrispondente al telefono di una persona. Invece, si tratta di un segnale visivo che consente a un utente di sapere che si tratta di una chiamata in uscita e non di una chiamata in arrivo contemporaneamente. Quando si distribuisce la chiamata tramite lavoro, è consigliabile informare gli utenti su questo numero di telefono globale e sul relativo significato.
    
3. L'utente che ha effettuato la chiamata preleva il telefono PBX. Skype for business avvia quindi la chiamata vocale al destinatario della chiamata. 
    
4. Quando il destinatario risponde, la chiamata vocale inizia. Se i due utenti avevano già in corso una sessione di messaggistica istantanea, può continuare.
    
### <a name="joining-a-conference-with-call-via-work"></a>Partecipare a una conferenza con chiamata tramite lavoro

Una chiamata tramite un utente può partecipare a una riunione pianificata facendo clic sull'URL della riunione. Skype for business quindi Visualizza un messaggio **di composizione verso l'esterno** fino a quando il servizio riunione compone il telefono PBX dell'utente. La chiamata tramite l'utente di lavoro quindi preleva il telefono PBX e si unisce alla riunione.
  
Una chiamata tramite l'utente di lavoro può anche usare l'opzione **Meet Now** in Skype for business per creare riunioni di Meet Now. L'utente visualizza quindi il messaggio **di chiamata in uscita** e il telefono PBX squilla.
  
Una chiamata tramite un utente di lavoro può anche comporre una riunione chiamando il numero del Bridge di conferenza dall'interno di Skype for business. Se è necessario un PIN per le conferenze, l'utente deve utilizzare il proprio telefono PBX per immettere il PIN.
  
### <a name="incoming-calls"></a>Chiamate in arrivo

Quando un utente abilitato per la chiamata tramite lavoro riceve una chiamata Skype for business, il telefono PBX e i client Skype for business dell'utente tutti squillano contemporaneamente (se l'utente ha configurato l'anello simultaneo). L'utente può accettare la chiamata selezionando il telefono PBX o facendo clic su **accetta** sulla notifica Skype for business. Se l'utente accetta la chiamata usando Skype for business, la finestra di Skype for business per la chiamata rimane aperta. Tuttavia, se l'utente accetta la chiamata riprendendo il telefono PBX, la finestra di notifica di Skype for business si chiude e non è presente alcuna sessione di Skype for business, ma solo la chiamata vocale sul telefono PBX.
  
Quando un utente abilitato per la chiamata tramite lavoro riceve una chiamata PBX, solo il telefono PBX squilla.
  
## <a name="limitations-of-call-via-work"></a>Limitazioni della chiamata tramite lavoro

Chiamata tramite lavoro è una soluzione vocale che richiede poca installazione hardware, ma presenta limitazioni rispetto alle funzionalità disponibili in Full Enterprise Voice o Remote Call Control. La chiamata tramite lavoro presenta le limitazioni seguenti:
  
- Se una chiamata tramite un utente di lavoro ha configurato l'inoltro di chiamata alla chiamata tramite il numero di callback del lavoro e qualcuno tenta di invitare questo utente a una riunione in base al numero di telefono dell'utente, l'invito non raggiungerà l'utente. È consigliabile educare gli utenti a invitare i partecipanti alle riunioni facendo clic sul nome e non sul numero di telefono. 
    
- La funzionalità Enhanced 911 e la traccia delle chiamate non consono disponibili durante la chiamata tramite le chiamate di lavoro.
    
- Gli utenti abilitati per la chiamata tramite lavoro non possono utilizzare le funzionalità di delega, chiamata del team o Response Group.
    
- Gli utenti di Call by work non possono usare Skype for business per registrare una riunione, disattivare o riattivare la chiamata, trattenere o trasferire la chiamata o utilizzare il parcheggio di chiamata.
    
- Gli utenti non possono utilizzare la chiamata tramite lavoro per accedere ai messaggi di segreteria telefonica PBX.
    
- Gli utenti di Call by work non possono inoltrare una sessione che è stata avviata come chiamata vocale a una riunione di collaborazione che include comunicazioni quali video, PowerPoint, lavagna o una nota.
    
- Gli utenti della chiamata tramite lavoro non possono aggiungere altri utenti a una chiamata di 2 persone.
    
- Nessun supporto per l'accoppiamento telefono da scrivania o il plug-in VDI.
    
- Se un utente effettua o risponde a una chiamata utilizzando il telefono PBX (e non utilizza la finestra di Skype for business), non vi sarà alcun registro della chiamata.
    
- Se il sistema PBX non supporta il **riferimento con sostituisce**, si verificherà il comportamento seguente. Quando si effettua una chiamata tramite chiamata di lavoro, se l'utente trasferisce la chiamata in uscita dal telefono PBX, la finestra di chiamata non scompare dalla finestra di Skype for business. Se l'utente chiude la finestra di chiamata, la chiamata tra la destinazione di trasferimento e il cessionario verrà terminata. 
    
## <a name="prerequisites-for-call-via-work"></a>Prerequisiti per la chiamata tramite lavoro

Per consentire agli utenti di effettuare chiamate tramite lavoro, è necessario disporre di alcuni prerequisiti. Per ulteriori informazioni su questi prerequisiti e per i passaggi su come abilitare gli utenti per la chiamata tramite lavoro, vedere [deploy Call by work in Skype for Business Server 2015](../../deploy/deploy-call-via-work.md). 
  
## <a name="see-also"></a>Vedere anche

[Pianificare il controllo delle chiamate remote in Skype for business](remote-call-control.md)
  
[Distribuire la chiamata tramite il lavoro in Skype for Business Server 2015](../../deploy/deploy-call-via-work.md)

