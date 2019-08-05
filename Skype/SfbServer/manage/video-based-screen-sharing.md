---
title: Condivisione dello schermo basata su video per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: Informazioni sulla pianificazione e la configurazione di Skype for Business Server per la condivisione dello schermo basata su video (VbSS)
ms.openlocfilehash: ae2cc683148fdb2a2cb80e3fe3cf25a698a56c00
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2019
ms.locfileid: "36195870"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a>Condivisione dello schermo basata su video per Skype for Business Server 
 
La condivisione dello schermo basata su video (VbSS) in Skype for Business Server 2015 è ora disponibile per il download: [aggiornamento cumulativo di Skype for Business server 2015 KB3061064](https://www.microsoft.com/en-us/download/details.aspx?id=47690). VbSS è incluso in Skype for Business Server 2019.
  
La condivisione dello schermo basata su video o VbSS è stata disattivata dalla condivisione dello schermo di Lync. La differenza tra VbSS e la condivisione dello schermo tradizionale ha a che fare con i protocolli sottostanti usati e in che cosa eccellono. La condivisione dello schermo usa il protocollo RDP (Remote Desktop Protocol), che è ideale per creare migliaia di sessioni da 1 a 1 tra i computer delle persone. La tecnologia più recente, VbSS, userà il protocollo UDP (User Datagram Protocol).
  
Skype for Business Server ha voluto migliorare le persone 1-a-1 e le loro conversazioni da 1 a molti (multi-party) e le loro esperienze di riunione. VbSS fa uso della piattaforma multimediale (che si basa su UDP come protocollo sottostante), con l'obiettivo di migliorare i tempi di avvio del video, la qualità della visualizzazione di quello che si sta guardando (soprattutto se quello che si sta guardando si sta muovendo velocemente) e l'affidabilità complessiva.
  
Parte dell'obiettivo del miglioramento della condivisione dello schermo è che le transizioni tra VbSS e RDP siano il più agevole possibile quando si verificano. Dato che VbSS è un aggiornamento della tecnologia sottostante usata per la condivisione dello schermo per Skype for Business Server, potrebbe essere difficile individuare la tecnologia che si sta sfruttando a meno che non si stia guardando i dettagli SIP nel traffico di rete o si stia condividendo contenuto che è in rapido spostamento o 3D. Se ad esempio il luogo di lavoro ha molti client legacy, RDP sarà ancora disponibile come failsafe per le riunioni e le conversazioni. Skype for Business Server usa la logica interna per decidere quale dei due metodi (VbSS o condivisione dello schermo tradizionale) applicare quando i client si connettono. RDP può e sarà sostituito da VbSS quando la situazione lo richiede, in modo che l'esperienza di visualizzazione non venga interrotta.
  
## <a name="planning"></a>Pianificazione

### <a name="vbss-pros-and-cons"></a>VbSS Pro e contro

Il passaggio a VbSS mira a apportare tre miglioramenti principali:
  
1. Rendere la condivisione dello schermo (fino al 5%) più affidabile rispetto al solo RDP.

2. Rendere più veloce la configurazione della sessione e l'esperienza video rispetto al solo RDP (configurazione in metà tempo, con un miglioramento di 6:1 in fotogrammi al secondo).

3. Funziona molto meglio del RDP in condizioni di larghezza di banda ridotta, anche quando si condividono contenuti ad alto contenuto, ad esempio grafica 3D.
    
Tieni presente che questi numeri si basano sull'ottimizzazione delle prestazioni e dell'integrità della rete e possono coinvolgere reti esterne alla tua, se i tuoi clienti si trovano su dispositivi mobili.
  
Dovresti anche tenere presente che una certa fedeltà/nitidezza del contenuto condiviso è stata scambiata per l'affidabilità, la velocità e l'efficienza. Nella maggior parte dei casi non sarà visibile agli utenti.
  
### <a name="ports-and-protocols"></a>Porte e protocolli

**Porte del server obbligatorie**

|**Ruolo del server**|**Nome servizio**|**Intervallo porta o porta**|**Protocollo**|**Note**|
|:-----|:-----|:-----|:-----|:-----|
|Server front-end  <br/> |Servizio di condivisione applicazioni di Skype for Business Server  <br/> |5065  <br/> |TCP  <br/> |Usato per le richieste di ascolto SIP in arrivo per la condivisione delle applicazioni.  <br/> |
|Server front-end  <br/> |Servizio di condivisione applicazioni di Skype for Business Server  <br/> |49152-65535  <br/> |TCP/UDP  <br/> |Intervallo di porte multimediali usato per la condivisione delle applicazioni.  <br/> |
   
**Porte client richieste**

|**Componente**|**Intervallo di porte**|**Protocollo**|**Note**|
|:-----|:-----|:-----|:-----|
|Client  <br/> |1024-65535  <br/> |TCP/UDP  <br/> |Condivisione applicazioni.  <br/> |
   
Se il QoS è abilitato per le porte multimediali seguenti e anche VbSS è abilitato, durante una conferenza che include la condivisione desktop l'AS MCU userà le impostazioni della porta video visualizzate in grassetto sotto per il traffico di condivisione dello schermo. 
  
> [!IMPORTANT]
> Queste impostazioni sono un caso speciale e queste impostazioni esatte devono essere usate durante l'implementazione di entrambe queste funzionalità. In questo articolo vengono ignorate altre impostazioni consigliate nella [documentazione per QoS](https://technet.microsoft.com/en-us/library/gg405409%28v=ocs.15%29.aspx). Per la condivisione delle applicazioni, è necessario specificare anche ASMCUSVC. exe nell'oggetto Criteri di ricerca QoS oltre a definire questi valori di porta. 
  
**Impostazioni richieste QoS/VbSS del server applicazioni**

|**Proprietà**|**Valore della porta**|**Protocollo**|
|:-----|:-----|:-----|
|AudioPortStart  <br/> |49152  <br/> |UDP  <br/> |
|AudioPortCount  <br/> |8348  <br/> |UDP  <br/> |
|**VideoPortStart** <br/> |**57501** <br/> |UDP  <br/> |
|**VideoPortCount** <br/> |**8034** <br/> |UDP  <br/> |
|AppSharingPortStart  <br/> |40803  <br/> |TCP  <br/> |
|AppSharingPortCount  <br/> |8348  <br/> |TCP  <br/> |
   
### <a name="capacity-planning"></a>Pianificazione della capacità

Ogni server front-end che usa Skype for Business Server 2015 cumulativo Update 2 (CU2) o versioni successive supporta fino a 375 partecipanti per la condivisione dello schermo usando RDP (anche se solo 250 per riunione). Questa capacità non cambia post-CU3, quando viene introdotto e usato VbSS.
  
Detto questo, abbiamo eseguito test sulle prestazioni e sulle sollecitazioni nel nostro laboratorio e le misure seguenti devono essere considerate anche in relazione alla propria distribuzione (a seconda dell'uso, ovviamente).
  
Presupponendo
  
- Si usa Skype for Business Server 2015 CU2 o versione successiva nella distribuzione.
    
- Tutti gli utenti dell'ambiente Skype for Business Server hanno risoluzioni dello schermo superiori a 1920x1080.
    
A piena capacità (che, come indicato in precedenza, è 375 partecipanti alla condivisione dello schermo per front end server in totale, anche se solo 250 per riunione), il server front-end può usare ~ 89% della scheda di rete 1 Gigabit. Il motivo è che la tecnologia di condivisione dello schermo esistente in Skype for Business Server CU2 (RDP) trasmette il contenuto su schermo alla risoluzione nativa del PC del relatore. Quindi, con le risoluzioni dello schermo più alte in factoring, potresti già provare i colli di bottiglia della rete per la condivisione dello schermo con Skype for Business Server 2015 CU2.
  
Per ovviare a questo problema, potrebbe essere utile una o più delle opzioni seguenti:
  
- Aggiornare il server front-end da una scheda di rete 1 Gigabit a una scheda Ethernet da 10 Gigabit.

- Aumentare il numero di server front-end per il traffico di bilanciamento del carico.

- Limitare la larghezza di banda (bitrate) usata per VbSS e RDP mettendo un tappo sulla larghezza di banda massima usata da entrambi i canali.
    
I numeri in questa tabella sono influenzati da singole reti e dal contenuto condiviso. Provare a stabilire le previsioni per la rete o le reti.
  
|**Contenuto 1080p**|**Media RDP**|**Picco RDP**|**Media VbSS**|**VbSS picco**|
|:-----|:-----|:-----|:-----|:-----|
|PPT  <br/> |200kbps  <br/> |12Mbps  <br/> |100kbps  <br/> |3Mbps  <br/> |
|CAD  <br/> |3Mbps  <br/> |7mbps  <br/> |1Mbps  <br/> |3Mbps  <br/> |
|Video  <br/> |5Mbps  <br/> |7mbps  <br/> |1.3 Mbps  <br/> |2.2 Mbps  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a>Requisiti di larghezza di banda di rete per il traffico multimediale

La larghezza di banda di VbSS è:
  
|**Codec video**|**Risoluzione e proporzioni**|**Velocità in bit (Kbps) massimo del payload video**|**Velocità in bit del payload video minimo (Kbps)**|
|:-----|:-----|:-----|:-----|
|H. 264  <br/> |1920x1080 (16:9)  <br/> (Le proporzioni dipendono dalla risoluzione del monitor del condivisore e non sempre saranno 16:9)  <br/> |4000  <br/> |1500  <br/> |
   
## <a name="clients-and-servers-support"></a>Supporto di client e server

La condivisione dello schermo basata su video richiede Skype for Business Server 2015 CU3 o versioni successive e una versione corrente dei client di supporto elencati nel [confronto delle caratteristiche del client mobile per il supporto di Skype for business](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) e [Meetings](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing). 
  
Ci sono situazioni in cui la condivisione dello schermo passerà al protocollo RDP, ad esempio:
  
- Se l'account è ospitato in un ambiente in cui ASMCU non soddisfa la build minima che supporta VbSS.
- Se una persona che usa una versione precedente del client Skype for business si unisce alla sessione, ad esempio chiunque usi una versione client di Windows inferiore a 16.0.6330.1000, i dispositivi di sistema room di Skype for business o le app per dispositivi mobili Skype for business. 
- Se un utente sta condividendo da Skype for Business Web App.
- Se qualcuno usa Skype for business per Mac e non è ospitato in Skype for business online o in Skype for Business Server 2015 con l'aggiornamento cumulativo di luglio 2018 (o versioni successive).
- Se qualcuno avvia qualsiasi programma/condivisione di Windows.
- Se qualcuno avvia la registrazione della sessione.
- Se un utente richiama il controllo dello schermo remoto durante la sessione. 
- Riunioni con più di 250 partecipanti (dove VbSS non è attualmente supportato).

Tieni presente che una volta che la sessione passa a RDP, la transizione non verrà restituita a VbSS. Anche in questo caso, la transizione da VbSS deve essere senza soluzione di continuità e, con la speranza, non sarà facile da individuare nella maggior parte delle situazioni.
    
> [!NOTE]
> Non è supportato il blocco o il tentativo di bloccare la transizione da VbSS a RDP in Skype for business per la condivisione dello schermo. 
  
## <a name="enabling-disabling-and-configuring-vbss"></a>Abilitazione, disabilitazione e configurazione di VbSS

La cosa più importante è che, dopo aver installato l'aggiornamento cumulativo 3 di Skype for Business Server 2015 (CU3) o versione successiva, tutti gli utenti saranno abilitati per l'attivazione di VbSS da 1 a 1 e di più parti per impostazione predefinita. Questo problema può risultare problematico se si ha un motivo per cui questa funzionalità non è abilitata per tutti gli utenti. In questo caso, puoi usare questi passaggi per disabilitare gli utenti (la procedura per l'abilitazione degli utenti seguirà):
  
### <a name="how-to-disable-users-from-using-vbss"></a>Come disabilitare gli utenti dall'uso di VbSS

- Puoi assegnare un criterio utente che non consenta a VbSS di usare VbSS eseguendo questo cmdlet in Skype for Business Management Console (Sostituisci [PolicyName] con i criteri per cui stai eseguendo questa operazione):
    
  ```
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- È anche possibile aggiornare i criteri di conferenza globale, che influiranno su tutti gli utenti senza un criterio assegnato:
    
  ```
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    Per altre informazioni su questo comando, vedere [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
    
- Se è necessario disattivare completamente VbSS, è possibile eseguire questo comando:
    
  ```
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    Per altre informazioni su questo comando, vedere [Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).
    
> [!NOTE]
> In una riunione Skype for business a più parti, tutti gli endpoint client rispetteranno l'impostazione del criterio per l'organizzatore della riunione. 
  
### <a name="how-to-enable-users-to-use-vbss"></a>Come consentire agli utenti di usare VbSS

- Puoi assegnare un criterio utente specifico che consente a VbSS di usare VbSS eseguendo questo cmdlet in Skype for Business Management Console (Sostituisci [PolicyName] con i criteri per cui stai eseguendo questa operazione):
    
  ```
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- È anche possibile aggiornare i criteri di conferenza globale, che influiranno su tutti gli utenti senza un criterio assegnato:
    
  ```
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    Per altre informazioni su questo comando, vedere [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
    
- Se devi riattivare VbSS dopo averlo disattivato (è attivato per impostazione predefinita), puoi eseguire questo comando:
    
  ```
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    Per altre informazioni su questo comando, vedere [Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).
    
> [!NOTE]
> In una riunione Skype for business multiparte, tutti gli endpoint client rispetteranno l'impostazione del criterio per l'organizzatore della riunione. 
  
## <a name="see-also"></a>Vedere anche

[Skype for Business Server 2015 aggiornamento cumulativo KB3061064](https://www.microsoft.com/en-us/download/details.aspx?id=47690)
  
[La condivisione dello schermo basata su video (VBSS) è disponibile in Skype for Business Server 2015](https://support.microsoft.com/en-us/kb/3170163)
