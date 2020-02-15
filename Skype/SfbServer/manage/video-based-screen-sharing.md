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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: Informazioni sulla pianificazione e la configurazione di Skype for Business Server per la condivisione dello schermo basata su video (VbSS)
ms.openlocfilehash: d6b66da2994db892bc193103bca75e844c62197f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42009569"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a>Condivisione dello schermo basata su video per Skype for Business Server 
 
La condivisione dello schermo basata su video (VbSS) in Skype for Business Server 2015 è ora disponibile per il download: [KB3061064 dell'aggiornamento cumulativo di Skype for Business server 2015](https://www.microsoft.com/download/details.aspx?id=47690). VbSS è incluso in Skype for Business Server 2019.
  
La condivisione dello schermo basata su video, o VbSS, è cresciuta dalla condivisione dello schermo di Lync. La differenza tra VbSS e la condivisione dello schermo tradizionale ha a che fare con i protocolli sottostanti utilizzati e in che modo eccellono. La condivisione dello schermo utilizza il protocollo RDP (Remote Desktop Protocol), che è molto utile per creare migliaia di sessioni da 1 a 1 tra i computer delle persone. La tecnologia più recente, VbSS, utilizzerà il protocollo UDP (User Datagram Protocol).
  
Skype for Business Server ha voluto migliorare le persone da 1 a 1 e le loro conversazioni da 1 a molti (multi-party) e le esperienze di riunione. VbSS si avvale della piattaforma multimediale (che si basa su UDP come protocollo sottostante), con l'obiettivo di migliorare i tempi di avvio del video, la qualità di visualizzazione di quello che stai guardando (soprattutto se quello che stai guardando si sta spostando velocemente) e l'affidabilità complessiva.
  
Parte dell'obiettivo del miglioramento della condivisione dello schermo consiste nel fatto che le transizioni tra VbSS e RDP siano il più possibile agevoli quando si verificano. Poiché VbSS è un aggiornamento alla tecnologia sottostante utilizzata per la condivisione dello schermo per Skype for Business Server, potrebbe essere difficile rilevare la tecnologia che si sta sfruttando, a meno che non si stia guardando i dettagli SIP nel traffico di rete o che si stia condividendo contenuti che è in rapido movimento o 3D. Se, ad esempio, il luogo di lavoro ha un sacco di client legacy, RDP sarà ancora disponibile come failsafe per le riunioni e le conversazioni. Skype for Business Server utilizza la logica interna per decidere quale dei due metodi (VbSS o la condivisione dello schermo tradizionale) applicare quando i client si connettono. RDP può e verrà sostituito da VbSS quando la situazione lo richiede, in modo che l'esperienza di visualizzazione non venga interrotta.
  
## <a name="planning"></a>Pianificazione

### <a name="vbss-pros-and-cons"></a>Vantaggi e svantaggi di VbSS

Il passaggio a VbSS ha lo scopo di apportare tre miglioramenti fondamentali:
  
1. Rendere la condivisione dello schermo (fino al 5%) maggiore affidabilità rispetto al solo PSR.

2. Rendere più veloce l'installazione e l'esperienza video della sessione rispetto a RDP da solo (programma di installazione in metà tempo, con un miglioramento di 6:1 in fotogrammi al secondo).

3. È molto più efficace rispetto al PSR in condizioni di larghezza di banda ridotta, anche quando si condividono contenuto ad alta risoluzione, ad esempio grafica 3D.
    
Tenere presente che questi numeri fanno affidamento sull'integrità e sulla corretta ottimizzazione delle prestazioni della rete e possono coinvolgere le reti esterne ai propri utenti, se i client sono su dispositivi mobili.
  
È inoltre necessario tenere presente che la fedeltà e la nitidezza del contenuto condiviso sono state scambiate per l'affidabilità, la velocità e l'efficienza. Nella maggior parte dei casi questo non sarà facilmente visibile agli utenti.
  
### <a name="ports-and-protocols"></a>Porte e protocolli

**Porte server obbligatorie**

|**Ruolo del server**|**Nome del servizio**|**Porta o intervallo di porte**|**Protocollo**|**Note**|
|:-----|:-----|:-----|:-----|:-----|
|Front End Server  <br/> |Servizio di condivisione applicazioni di Skype for Business Server  <br/> |5065  <br/> |TCP  <br/> |Utilizzata per le richieste di attesa SIP in arrivo per la condivisione delle applicazioni.  <br/> |
|Front End Server  <br/> |Servizio di condivisione applicazioni di Skype for Business Server  <br/> |49152-65535  <br/> |TCP/UDP  <br/> |Intervallo di porte di attesa multimediali per la condivisione delle applicazioni.  <br/> |
   
**Porte client richieste**

|**Componente**|**Intervallo di porte**|**Protocollo**|**Note**|
|:-----|:-----|:-----|:-----|
|Client  <br/> |1024-65535  <br/> |TCP/UDP  <br/> |Condivisione applicazioni.  <br/> |
   
Se QoS è abilitato per le seguenti porte multimediali e VbSS è abilitato, durante una conferenza che include la condivisione del desktop come MCU utilizzerà le impostazioni della porta video visualizzate in grassetto in basso per il traffico di condivisione dello schermo. 
  
> [!IMPORTANT]
> Queste impostazioni sono un caso speciale e devono essere utilizzate per l'implementazione di entrambe queste funzionalità. Questo sostituisce altre impostazioni consigliate nella [documentazione per QoS](https://technet.microsoft.com/library/gg405409%28v=ocs.15%29.aspx). Per la condivisione delle applicazioni, è inoltre necessario specificare ASMCUSVC. exe nell'oggetto Criteri di gruppo QoS oltre a definire questi valori di porta. 
  
**Impostazioni necessarie per il server applicazioni QoS/VbSS**

|**Proprietà**|**Valore porta**|**Protocollo**|
|:-----|:-----|:-----|
|AudioPortStart  <br/> |49152  <br/> |UDP  <br/> |
|AudioPortCount  <br/> |8348  <br/> |UDP  <br/> |
|**VideoPortStart** <br/> |**57501** <br/> |UDP  <br/> |
|**VideoPortCount** <br/> |**8034** <br/> |UDP  <br/> |
|AppSharingPortStart  <br/> |40803  <br/> |TCP  <br/> |
|AppSharingPortCount  <br/> |8348  <br/> |TCP  <br/> |
   
### <a name="capacity-planning"></a>Pianificazione della capacità

Ogni front end server che esegue Skype for Business Server 2015 Cumulative Update 2 (CU2) o versioni successive supporta fino a 375 partecipanti per la condivisione dello schermo tramite RDP (anche se solo 250 per riunione). Questa capacità non cambia post-CU3, quando viene introdotta e utilizzata VbSS.
  
Detto questo, sono stati eseguiti test di prestazioni e stress nel laboratorio e sono state esaminate anche le misure seguenti in relazione alla propria distribuzione (a seconda dell'utilizzo, ovviamente).
  
Presupponendo
  
- Si sta utilizzando Skype for Business Server 2015 CU2 o versione successiva nella distribuzione.
    
- Tutti gli utenti dell'ambiente Skype for Business Server dispongono di risoluzioni dello schermo superiori a 1920x1080.
    
A piena capacità (come indicato in alto, è 375 partecipanti alla condivisione dello schermo per front end server in totale, anche se solo 250 per riunione), il front end server può essere utilizzato ~ 89% del 1 gigabit della scheda di rete. Ciò è dovuto al fatto che la tecnologia di condivisione dello schermo esistente in Skype for Business Server CU2 (RDP) trasmette il contenuto sullo schermo alla risoluzione nativa del PC del relatore. Con le risoluzioni dello schermo più elevate, è possibile che si verifichino già dei colli di bottiglia per la condivisione dello schermo con Skype for Business Server 2015 CU2.
  
Per attenuare la procedura, è possibile che siano utili una o più delle opzioni seguenti:
  
- Aggiornare il front end server da una scheda di rete da 1 Gigabit a una scheda Ethernet da 10 Gigabit.

- Aumentare il numero di front end server per il traffico di bilanciamento del carico.

- Limitare la larghezza di banda (bitrate) utilizzata per VbSS e RDP inserendo un tappo sulla larghezza di banda massima utilizzata da entrambi i canali.
    
I numeri contenuti in questa tabella sono influenzati dalle singole reti e dal contenuto condiviso. Provare a stabilire le linee di base per la rete o le reti.
  
|**Contenuto 1080p**|**Media RDP**|**Picco RDP**|**VbSS media**|**Picco VbSS**|
|:-----|:-----|:-----|:-----|:-----|
|PPT  <br/> |200kbps  <br/> |12Mbps  <br/> |100kbps  <br/> |3Mbps  <br/> |
|CAD  <br/> |3Mbps  <br/> |7mbps  <br/> |1Mbps  <br/> |3Mbps  <br/> |
|Video  <br/> |5Mbps  <br/> |7mbps  <br/> |1,3 Mbps  <br/> |2.2 Mbps  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a>Requisiti di larghezza di banda di rete per il traffico multimediale

La larghezza di banda di VbSS è:
  
|**Codec video**|**Risoluzione e proporzioni**|**Velocità in bit massima del payload video (Kbps)**|**Velocità in bit di payload video minimo (Kbps)**|
|:-----|:-----|:-----|:-----|
|H. 264  <br/> |1920x1080 (16:9)  <br/> (Le proporzioni dipendono dalla risoluzione del monitor del condivisore e non saranno sempre 16:9)  <br/> |4000  <br/> |1500  <br/> |
   
## <a name="clients-and-servers-support"></a>Supporto per client e server

La condivisione dello schermo basata su video richiede Skype for Business Server 2015 CU3 o versioni successive e una versione corrente dei client di supporto elencati nel [confronto delle caratteristiche dei client per dispositivi mobili per il supporto di Skype for business](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) e [Meetings](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing). 
  
Vi sono situazioni in cui la condivisione dello schermo verrà transizione a RDP, come:
  
- Se l'account è ospitato in un ambiente in cui ASMCU non soddisfa la build minima che supporta VbSS.
- Se un utente che usa una versione precedente del client Skype for business si unisce alla sessione, ad esempio chiunque utilizzi qualsiasi versione client di Windows più bassa di 16.0.6330.1000, i dispositivi di sistema di Skype for business room o le app per dispositivi mobili di Skype for business. 
- Se un utente sta condividendo da Skype for Business Web App.
- Se un utente utilizza Skype for business su Mac e non è ospitato su Skype for business online o su Skype for Business Server 2015 con l'aggiornamento cumulativo di luglio 2018 (o versione successiva).
- Se un utente avvia un programma o una condivisione di Windows.
- Se qualcuno inizia a registrare la sessione.
- Se un utente richiama il controllo dello schermo remoto durante la sessione. 
- Riunioni con più di 250 partecipanti (in cui VbSS non è attualmente supportato).

Tenere presente che una volta che la sessione è stata trasformata in RDP, la transizione non verrà restituita a VbSS. Anche in questo caso, la transizione da VbSS è destinata a essere trasparente e, con la speranza, non sarà facile da rilevare nella maggior parte delle situazioni.
    
> [!NOTE]
> Non è supportato per bloccare o tentare di bloccare la transizione da VbSS a RDP in condivisione dello schermo di Skype for business. 
  
## <a name="enabling-disabling-and-configuring-vbss"></a>Abilitazione, disabilitazione e configurazione di VbSS

La cosa importante è che, dopo aver installato l'aggiornamento cumulativo 3 (CU3) di Skype for Business Server 2015 o versione successiva, tutti gli utenti verranno abilitati per impostazione predefinita da 1 a 1 e da VbSS a più parti. Potrebbe essere problematico se si dispone di un motivo per cui questa funzionalità non è abilitata per tutti gli utenti. In tal caso, è possibile utilizzare questi passaggi per disabilitare gli utenti (i passaggi di abilitazione degli utenti seguiranno):
  
### <a name="how-to-disable-users-from-using-vbss"></a>Come disabilitare gli utenti dall'utilizzo di VbSS

- È possibile assegnare un criterio utente che non consenta VbSS a qualsiasi utente che non deve utilizzare VbSS eseguendo questo cmdlet nella console di gestione di Skype for business (sostituire [PolicyName] con il criterio per il quale si sta eseguendo questa operazione):
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- È inoltre possibile aggiornare il criterio di conferenza globale, che influenzerà tutti gli utenti senza un criterio assegnato:
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    Per ulteriori informazioni su questo comando, vedere [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
    
- Se è necessario disattivare completamente VbSS, è possibile eseguire il comando seguente:
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    Per ulteriori informazioni su questo comando, vedere [Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).
    
> [!NOTE]
> In una riunione di Skype for business con più partecipanti, tutti gli endpoint client rispetteranno l'impostazione del criterio per l'organizzatore della riunione. 
  
### <a name="how-to-enable-users-to-use-vbss"></a>Come abilitare gli utenti all'utilizzo di VbSS

- È possibile assegnare un criterio utente specifico che consenta a VbSS di tutti gli utenti che devono utilizzare VbSS eseguendo questo cmdlet nella console di gestione di Skype for business (sostituire [PolicyName] con il criterio per il quale si sta eseguendo questa operazione):
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- È inoltre possibile aggiornare il criterio di conferenza globale, che influenzerà tutti gli utenti senza un criterio assegnato:
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    Per ulteriori informazioni su questo comando, vedere [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
    
- Se è necessario attivare di nuovo VbSS dopo averla disattivata (è attivata per impostazione predefinita), è possibile eseguire questo comando:
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    Per ulteriori informazioni su questo comando, vedere [Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).
    
> [!NOTE]
> In una riunione Skype for business multi-party tutti gli endpoint client rispetteranno l'impostazione dei criteri per l'organizzatore della riunione. 
  
## <a name="see-also"></a>Vedere anche

[Aggiornamento cumulativo di KB3061064 per Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=47690)
  
[La condivisione dello schermo basata su video (VBSS) è disponibile in Skype for Business Server 2015](https://support.microsoft.com/kb/3170163)
