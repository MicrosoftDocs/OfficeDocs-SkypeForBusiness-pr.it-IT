---
title: Pianificare la chiamata tramite il lavoro in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a33ec637-9ac8-4cb7-b3b2-88d432efc078
description: Pianificazione della chiamata tramite il lavoro in Skype for Business Server, che consente l'integrazione tra Skype for business e il sistema telefonico PBX, in modo che gli utenti possano usare Skype for business per controllare i telefoni PBX.
ms.openlocfilehash: b2f0e57a33f6e194dc981b623a641850ed3c8de5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187757"
---
# <a name="plan-for-call-via-work-in-skype-for-business-server"></a>Pianificare la chiamata tramite il lavoro in Skype for Business Server
 
Pianificazione della chiamata tramite il lavoro in Skype for Business Server, che consente l'integrazione tra Skype for business e il sistema telefonico PBX, in modo che gli utenti possano usare Skype for business per controllare i telefoni PBX.
  
 **Chiamata tramite work** è una nuova funzionalità di Skype for Business Server che consente di integrare la soluzione Skype for business con i sistemi telefonici PBX esistenti. Un utente abilitato per la chiamata tramite lavoro può fare clic su Skype for business per chiamare un altro utente, all'interno della distribuzione o di un utente esterno. La chiamata viene completata con il telefono PBX dell'utente. Ciò consente a un utente con un telefono PBX di includere l'audio nelle conversazioni Rich Skype for business. Nelle versioni precedenti del controllo delle chiamate remote di Lync Server era disponibile una funzionalità che consente agli utenti di controllare i telefoni PBX con Lync Server. In Skype for Business Server questa funzionalità è stata sostituita da chiamata tramite lavoro.
  
Chiamata tramite lavoro consente di seguire gli utenti di telefoni PBX
  
- Esperienza di chiamata a portata di clic, con l'audio fornito tramite il telefono PBX.
    
- Presenza, ricerca utente e integrazione di messaggistica istantanea, ad esempio due chiamate tramite utenti di lavoro in una sessione di messaggistica istantanea, possono aggiungere audio alla sessione, con l'audio fornito tramite i telefoni PBX.
    
- Possibilità di aggiungere messaggi istantanei, condivisione di applicazioni e trasferimento di file a una chiamata tramite chiamata di lavoro.
    
- Funzionalità di partecipazione alla riunione con un clic
    
## <a name="how-it-works"></a>Funzionamento

Chiamata tramite lavoro usa Unified Communications Web API (UCWA) come agente utente back-to-back (B2BUA) tra il sistema PBX e la distribuzione di Skype for Business Server, in modo che non sia necessario un gateway per l'applicazione di telecomunicazioni (CSTA) supportato da computer per la connessione Skype for Business Server con il sistema PBX. UCWA è un servizio introdotto in versioni precedenti di Lync Server per abilitare la connettività con client mobili e Web e viene installato automaticamente in ogni server front-end.
  
### <a name="call-workflow-for-a-call-via-work-call"></a>Chiamare il flusso di lavoro per una chiamata tramite chiamata lavorativa

Di seguito viene illustrato il modo in cui un utente abilitato per la chiamata tramite lavoro può utilizzare Skype for Business Server per effettuare una chiamata:
  
![Mostra la procedura durante una chiamata tramite chiamata di lavoro; prima il chiamante fa clic per chiamare una persona nel client Skype for business; quindi il UCWA squilla il telefono del chiamante. Quando il chiamante preleva il telefono, viene chiamato il destinatario](../../media/050e88ed-e18e-40c0-84d5-b17fe40c305a.jpg)
  
1. L'utente seleziona un utente nel client Skype for business e fa clic sull'icona del telefono per chiamarli. Oppure, durante una conversazione di messaggistica istantanea, l'utente fa clic per chiamare l'utente con cui sta effettuando la sessione.
    
2. Il telefono PBX dell'utente che ha inserito la chiamata inizia a squillare. L'ID chiamante di questo telefono mostra un numero di telefono globale configurato per la visualizzazione nell'ID chiamante di tutti gli utenti che effettuano una chiamata tramite le chiamate di lavoro. Questo numero di telefono globale non è un numero di telefono effettivo che corrisponde al telefono di una persona. Si tratta invece di un segnale visivo che consente a un utente di sapere che si tratta di una chiamata in uscita e non di una chiamata in arrivo. Quando si distribuisce la chiamata tramite lavoro, è consigliabile informare gli utenti su questo numero di telefono globale e su cosa significa.
    
3. L'utente che ha effettuato la chiamata preleva il telefono PBX. Skype for business avvia quindi la chiamata vocale al chiamato. 
    
4. Quando il chiamato risponde, inizia la chiamata vocale. Se i due utenti hanno già eseguito una sessione di messaggistica istantanea, può continuare.
    
### <a name="joining-a-conference-with-call-via-work"></a>Partecipare a una conferenza con chiamata tramite lavoro

Una chiamata tramite l'utente del lavoro può partecipare a una riunione pianificata facendo clic sull'URL della riunione. Skype for business Mostra quindi un messaggio **di chiamata in uscita** fino a quando il servizio di riunione non compone il telefono PBX dell'utente. La chiamata tramite l'utente del lavoro quindi preleva il telefono PBX e partecipa alla riunione.
  
Una chiamata tramite l'utente del lavoro può anche usare l'opzione **riunione** immediata in Skype for business per creare riunioni riunione ora. L'utente visualizza quindi il messaggio **di chiamata in uscita** e il telefono PBX squilla.
  
Una chiamata tramite l'utente del lavoro può anche eseguire la chiamata a una riunione chiamando il numero del Bridge di conferenza in Skype for business. Se è necessario un PIN per la conferenza, l'utente deve usare il telefono PBX per immettere il PIN.
  
### <a name="incoming-calls"></a>Chiamate in arrivo

Quando un utente abilitato per la chiamata tramite lavoro riceve una chiamata Skype for business, il telefono PBX e i client Skype for business dell'utente squillano tutti contemporaneamente (se l'utente ha configurato l'anello simultaneo). L'utente può accettare la chiamata sollevando il telefono PBX o facendo clic su **accetta** nella notifica Skype for business. Se l'utente accetta la chiamata con Skype for business, la finestra di Skype for business per la chiamata rimane aperta. Ma se l'utente accetta la chiamata raccogliendo il telefono PBX, la finestra di notifica di Skype for business si chiude e non è disponibile una sessione Skype for business, solo la chiamata vocale tramite il telefono PBX.
  
Quando un utente abilitato per la chiamata tramite lavoro riceve una chiamata PBX, solo il telefono PBX squilla.
  
## <a name="limitations-of-call-via-work"></a>Limitazioni della chiamata tramite lavoro

La chiamata tramite lavoro è una soluzione vocale che richiede poca configurazione hardware, ma con limitazioni rispetto alle funzionalità disponibili in un controllo vocale completo o di chiamata remota. La chiamata tramite lavoro ha le seguenti limitazioni:
  
- Se una chiamata tramite l'utente del lavoro ha configurato l'inoltro di chiamata alla chiamata tramite il numero di callback del lavoro e qualcuno prova a invitare l'utente a una riunione in base al numero di telefono dell'utente, l'invito non raggiungerà l'utente. È consigliabile informare gli utenti di invitare i partecipanti alle riunioni facendo clic sul nome e non sul numero di telefono. 
    
- Le funzionalità avanzate di 911 e la traccia delle chiamate malevole non sono disponibili durante la chiamata tramite le chiamate lavorative.
    
- Gli utenti abilitati per la chiamata tramite lavoro non possono usare le caratteristiche di delega, chiamata del team o Response Group.
    
- Gli utenti della chiamata tramite lavoro non possono usare Skype for business per registrare una riunione, disattivare o riattivare la chiamata, tenere premuto o trasferire la chiamata o utilizzare Call Park.
    
- Gli utenti non possono usare la chiamata tramite lavoro per accedere ai messaggi della segreteria telefonica PBX.
    
- Gli utenti della chiamata tramite lavoro non possono escalation di una sessione iniziata come chiamata vocale a una riunione collaborativa che include comunicazioni come video, PowerPoint, lavagna o una nota.
    
- Gli utenti della chiamata tramite lavoro non possono aggiungere altri utenti a una chiamata di due persone.
    
- Nessun supporto per l'associazione telefono da scrivania o il plug-in VDI.
    
- Se un utente effettua o risponde a una chiamata usando il telefono PBX (e non usando la finestra di Skype for business), non ci saranno log della chiamata.
    
- Se il sistema PBX non supporta il **riferimento con Sostituisci**, si verificherà il comportamento seguente. Durante una chiamata tramite chiamata di lavoro, se l'utente trasferisce la chiamata in corso dal telefono PBX, la finestra di chiamata non scompare dalla finestra di Skype for business. Se l'utente chiude la finestra di chiamata, la chiamata tra la destinazione di trasferimento e il cessionario terminerà. 
    
## <a name="prerequisites-for-call-via-work"></a>Prerequisiti per la chiamata tramite lavoro

Per abilitare gli utenti per la chiamata tramite lavoro, è necessario disporre di alcuni requisiti preliminari. Per altre informazioni su questi prerequisiti e per istruzioni su come abilitare gli utenti per la chiamata tramite lavoro, vedere distribuire la [chiamata tramite lavoro in Skype for Business Server 2015](../../deploy/deploy-call-via-work.md). 
  
## <a name="see-also"></a>Vedere anche

[Pianificare il controllo delle chiamate remote in Skype for business](remote-call-control.md)
  
[Distribuire la funzionalità Chiamata tramite ufficio in Skype for Business Server 2015](../../deploy/deploy-call-via-work.md)

