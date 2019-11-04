---
title: Ripristino di emergenza del pool di front-end in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
description: Per il ripristino di emergenza, Skype for Business Server offre l'associazione in pool con il failover nel caso in cui un pool vada in calo.
ms.openlocfilehash: 3999b7b8c2dd9b5eea942779f09924c6b5a79210
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "37341932"
---
# <a name="front-end-pool-disaster-recovery-in-skype-for-business-server"></a>Ripristino di emergenza del pool di front-end in Skype for Business Server
 
Per il ripristino di emergenza, Skype for Business Server offre l'associazione in pool con il failover nel caso in cui un pool vada in calo.
  
Per le opzioni più affidabili per il ripristino di emergenza in Skype for Business Server, distribuire coppie di pool Front-end in due siti dislocati geograficamente. Ogni sito ha un pool Front-end che viene associato a un pool Front-End corrispondente nell'altro sito. Entrambi i siti sono attivi e il servizio di backup offre la replica dei dati in tempo reale per sincronizzare i pool. Vedere [distribuire pool Front-End associati per il ripristino di emergenza in Skype for Business Server](../../deploy/deploy-high-availability-and-disaster-recovery/front-end-pools-for-disaster-recovery.md) se si vuole implementare l'associazione del pool Front-end.
  
![Mostra i pool Front-end in due siti diversi, associati tra loro](../../media/f74533c0-a10e-4f18-85a8-b9a008497573.jpg)
  
Se il pool in un sito non riesce, è possibile eseguire il failover degli utenti da tale pool al pool nell'altro sito, che quindi serve tutti gli utenti in entrambi i pool. Per la pianificazione della capacità, è consigliabile progettare ogni pool per poter gestire il carico di lavoro di tutti gli utenti in entrambi i pool in caso di emergenza.
  
Due centri dati che includono pool Front-End combinati tra loro possono essere a qualsiasi distanza. È consigliabile associare due centri dati nella stessa area geografica mondiale, con collegamenti ad alta velocità tra di essi. 
  
È possibile avere due centri dati in tutte le aree del mondo, ma potrebbe causare una perdita di dati più elevata in caso di emergenza, a causa della latenza nella replicazione dei dati.
  
Quando si pianificano i pool da associare, è necessario ricordare che sono supportate solo le associazioni seguenti:
  
- I pool Enterprise Edition possono essere accoppiati solo con altri pool di Enterprise Edition. Allo stesso modo, i pool Standard Edition possono essere abbinati solo agli altri pool di Standard Edition.
    
- I pool fisici possono essere accoppiati solo con altri pool fisici. Allo stesso modo, i pool virtuali possono essere abbinati solo ad altri pool virtuali.
    
- I pool combinati devono eseguire lo stesso sistema operativo di base.
    
Né il generatore di topologie né la convalida della topologia impediscono l'associazione di due pool in modo da non seguire questi suggerimenti. Ad esempio, generatore di topologie consente di associare un pool Enterprise Edition a un pool di Standard Edition. Tuttavia, questi tipi di associazione non sono supportati.
  
## <a name="backup-registrar-relationships-and-survivable-branch-appliances"></a>Relazioni di registrazione di backup e Survivable Branch Appliance

Oltre a fornire un'abilità di ripristino di emergenza, due pool associati fungono da registrar di backup. Ogni pool può essere il backup solo per un altro pool Front-end.
  
Anche se le relazioni di backup tra due pool Front-end devono essere di 1:1 e simmetriche, ogni pool Front-end può essere comunque anche il registrar per qualsiasi numero di appliance Survivable Branch.
  
Tieni presente che Skype for business non estende il supporto per il ripristino di emergenza agli utenti ospitati in un Survivable Branch Appliance. Se un pool Front-end che funge da backup per un appliance Survivable Branch si abbassa, gli utenti che hanno eseguito l'accesso a Survivable Branch Appliance entrano in modalità di resilienza anche se gli utenti ospitati nel pool Front-end non vengono eseguiti nel pool Front-End di backup.
  
## <a name="recovery-time-for-pool-failover-and-pool-failback"></a>Tempo di ripristino per il failover e il failback dei pool

Per il failover del pool e il failback del pool, la destinazione ingegneristica per l'obiettivo del tempo di recupero (RTO) è di 15-20 minuti. Questo è il tempo necessario per il failover, dopo che gli amministratori hanno determinato che si è verificato un disastro ed è stata avviata la procedura di failover. Non include il tempo per gli amministratori di valutare la situazione e prendere una decisione, né include il tempo per cui gli utenti possono accedere di nuovo dopo il completamento del failover.
  
Per il failover del pool e il failback del pool, la destinazione ingegneristica per l'obiettivo del punto di ripristino (RPO) è di 5 minuti. Rappresenta la misura temporale dei dati che potrebbero essere persi a causa del disastro causato dalla latenza della replica del servizio di backup. Ad esempio, se un pool scende alle 10:00 A.M. e RPO è di 5 minuti, i dati vengono scritti nel pool tra 9:55 A.M. e 10:00. M. potrebbe non essere stato replicato nel pool di backup e andrebbe perduto.
  
Tutti i numeri di RTO e RPO in questo documento presuppongono che i due centri dati si trovino all'interno della stessa area geografica con il trasporto ad alta velocità e a bassa latenza tra i due siti. Questi numeri vengono misurati per un pool con 40.000 utenti attivi simultaneamente e 200.000 utenti abilitati per Skype for business rispetto a un modello di utente predefinito in cui non è presente alcun backlog nella replica dei dati. Sono soggetti a modifiche in base al test delle prestazioni e alla convalida.
  
## <a name="central-management-store-failover"></a>Failover dell'archivio di gestione centrale

L'archivio di gestione centrale contiene i dati di configurazione relativi ai server e ai servizi nella distribuzione. Ogni distribuzione di Skype for Business Server include un unico Central Management store, ospitato dal server back-end di un pool Front-end.
  
Se si associa il pool che ospita l'Central Management store, nel pool di backup è configurato un database di archiviazione centrale di backup. In qualsiasi momento, uno dei due database di Central Management store è attivo e l'altro è in standby. Il contenuto viene replicato dal servizio di backup dal database attivo in standby.
  
![Mostra due pool Front-End, uno con lo Store CMS attivo e l'altro con l'archivio CMS di backup passivo](../../media/aa479398-eb56-4854-8d50-1eff39c58a56.jpg)
  
Durante un failover del pool che include il pool che ospita l'Central Management store, è necessario avere esito negativo su Central Management Store prima di avere esito negativo sul pool Front-end.
  
Una volta riparato il disastro, non è necessario eseguire il failover dell'Central Management store. L'Central Management store può rimanere nel pool in cui è stato omesso.
  
Gli obiettivi di progettazione per il failover di Central Management store sono di 5 minuti per l'obiettivo del tempo di recupero (RTO) e di 5 minuti per l'obiettivo del punto di ripristino (RPO).
  
## <a name="front-end-pool-pairing-data-security"></a>Sicurezza dei dati per l'abbinamento dei pool Front End

Il servizio di backup trasferisce continuamente i dati degli utenti e il contenuto delle conferenze tra due pool Front-End associati. I dati degli utenti contengono URI SIP degli utenti, nonché pianificazioni per conferenze, elenchi di contatti e impostazioni. Il contenuto della conferenza include i caricamenti di Microsoft PowerPoint e le lavagne usate nelle conferenze.
  
Dal pool di origine questi dati vengono esportati dall'archivio locale, zippati e quindi trasferiti nel pool di destinazione, in cui vengono decompressi e importati nello spazio di archiviazione locale. Il servizio di backup presuppone che il collegamento delle comunicazioni tra i due centri dati si trovi all'interno della rete aziendale protetta da Internet. Non crittografa i dati trasferiti tra i due centri dati, né i dati vengono incapsulati in modo nativo all'interno di un protocollo sicuro, ad esempio HTTPS. Di conseguenza, è possibile un attacco di tipo man-in-the-Middle da parte di personale interno della rete aziendale.
  
Qualsiasi organizzazione che distribuisce Skype for Business Server in più centri dati e usa la funzionalità di ripristino di emergenza deve garantire che il traffico tra i centri dati sia protetto dalla propria Intranet aziendale. Le aziende che preoccupano la protezione dagli attacchi interni devono garantire i collegamenti di comunicazione tra i centri dati. Si tratta di un requisito standard che consente anche di Protech molti altri tipi di dati sensibili aziendali trasferiti tra i centri dati.
  
Mentre il rischio di attacchi man-in-the-Middle all'interno della rete aziendale esiste, è relativamente contenuto rispetto a esporre il traffico a Internet. In particolare, i dati utente esposti dal servizio di backup, ad esempio URI SIP, sono in genere disponibili per tutti i dipendenti della società tramite altri mezzi, ad esempio la Rubrica globale o un altro software di directory. Di conseguenza, lo stato attivo dovrebbe essere la protezione della WAN tra i due centri dati quando viene usato il servizio di backup per copiare i dati tra i due pool associati.
  
### <a name="mitigating-security-risks"></a>Attenuazione dei rischi per la sicurezza

Sono disponibili diversi modi per migliorare la protezione della sicurezza per il traffico dei servizi di backup. Questo intervallo consiste nell'limitare l'accesso ai Data Center per proteggere il trasporto WAN tra i due centri dati. Nella maggior parte dei casi, le aziende che distribuiscono Skype for Business Server potrebbero già disporre dell'infrastruttura di sicurezza necessaria. Per le aziende che cercano indicazioni, Microsoft offre una soluzione come esempio di creazione di un'infrastruttura IT sicura. Per informazioni dettagliate, [https://go.microsoft.com/fwlink/p/?LinkId=268544](https://go.microsoft.com/fwlink/p/?LinkId=268544)vedere. 
  
Non comprendiamo che sia l'unica soluzione, né implichiamo che sia la soluzione preferita per Skype for Business Server. È consigliabile che i clienti aziendali scelgano la soluzione più adatta alle proprie esigenze specifiche, in base all'infrastruttura e ai requisiti di sicurezza IT. L'esempio di soluzione Microsoft usa IPSec e criteri di gruppo per l'isolamento del server e del dominio.
  
Un'altra possibile soluzione consiste nell'usare IPSec solo per proteggere i dati inviati dal servizio di backup stesso. Se si sceglie questo metodo, è necessario configurare le regole IPSec per il protocollo SMB per i server seguenti, dove pool A e pool B sono due pool Front-End associati.
  
- Servizio SMB (TCP/445) da ogni server front-end del pool a all'archivio di file usato dal pool B.
    
- Il servizio SMB (TCP/445) di ogni server front-end nel pool B nell'archivio file usato dal pool A.
    
> [!CAUTION]
>  IPsec non è concepito come sostituzione per la sicurezza a livello di applicazione, ad esempio SSL/TLS. Un vantaggio dell'uso di IPsec è che può assicurare la sicurezza del traffico di rete per le applicazioni esistenti senza doverle cambiare. Le aziende che vogliono garantire semplicemente il trasporto tra i due centri dati devono consultare i rispettivi fornitori di hardware per la rete in merito alle modalità di configurazione delle connessioni WAN sicure tramite l'equipaggiamento del fornitore.
  
## <a name="see-also"></a>Vedere anche

[Distribuire pool Front End associati per il ripristino di emergenza in Skype for Business Server](../../deploy/deploy-high-availability-and-disaster-recovery/front-end-pools-for-disaster-recovery.md)
