---
title: Pianificare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server 2015
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: d9aa622a-95a3-4d8e-8d49-cbfe183f25bf
description: 'Riepilogo: leggere questo argomento per informazioni su come pianificare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server 2015.'
---

# <a name="plan-for-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Pianificare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server 2015
 
**Riepilogo:** Leggere questo argomento per informazioni su come pianificare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server 2015.
  
La disponibilità elevata e il ripristino di emergenza per il server Chat persistente richiedono risorse aggiuntive oltre a quanto in genere necessario per il funzionamento completo. 
  
> [!NOTE]
> L'SQL gruppi di disponibilità AlwaysOn non è supportato con i database del server Chat persistente. 

> [!NOTE] 
> La chat persistente è disponibile Skype for Business Server 2015, ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in Teams. Per ulteriori informazioni, vedere [Introduzione all'Microsoft Teams aggiornamento](/microsoftteams/upgrade-start-here). Se è necessario utilizzare persistent chat, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità Teams o continuare a usare Skype for Business Server 2015. 
  
## <a name="resource-requirements"></a>Requisiti in termini di risorse

Prima di configurare il server Chat persistente per la disponibilità elevata e il ripristino di emergenza, assicurarsi di disporre delle risorse aggiuntive seguenti. 
  
- Un'istanza di database dedicata che si trova nello stesso data center fisico in cui si trova il front-end principale del servizio server Chat persistente. Questo database fungerà da SQL Server mirror per il database di Persistent Chat primario. Facoltativamente, designare un SQL Server aggiuntivo da utilizzare come controllo del mirroring se si desidera un failover automatico nel database mirror.
    
- Un'istanza di database dedicata nell'altro data center fisico. Questo database fungerà da SQL Server database secondario di log shipping per il database nel data center principale.
    
- Un'istanza di database dedicata da utilizzare come SQL Server mirror per il database secondario. Facoltativamente, designare un'SQL Server al server come server di controllo del mirroring. Entrambi devono trovarsi nello stesso data center fisico del database secondario.
    
- Se la conformità del server Chat persistente è abilitata, sono necessarie altre tre istanze di database dedicate. La distribuzione è identica a quella descritta in precedenza per il database di Persistent Chat. Sebbene sia possibile per il database di conformità condividere la stessa istanza SQL Server del database di Persistent Chat, sono consigliate istanze autonome per la disponibilità elevata e il ripristino di emergenza.
    
- È necessario creare e designare una condivisione file per i SQL Server log shipping. Tutti SQL server in entrambi i data center che eseguono database di Persistent Chat devono disporre dell'accesso in lettura/scrittura a questa condivisione file. Tale condivisione non è definita come parte di un ruolo FileStore.
    
- Condivisione file nel server database secondario da utilizzare come cartella di destinazione per i registri delle transazioni SQL Server copiati dalla condivisione file del server principale.
    
## <a name="disaster-recovery-and-high-availability-solutions"></a>Soluzioni di ripristino di emergenza e disponibilità elevata

Skype for Business Server supporta più modalità di disponibilità elevata per i server back-end, incluso il mirroring del database. Per ulteriori informazioni, vedere [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md). 
  
La soluzione di ripristino di emergenza per il server Chat persistente descritta in questo argomento si basa su un pool di server Chat persistente estesa. Non è necessario utilizzare una VLAN (Virtual Local Area Network) estesa. Estendendo un pool di server Chat persistente, si configura logicamente un pool nella topologia, ma si posizionano fisicamente i server nel pool in due data center diversi. È possibile SQL Server il mirroring del database nello stesso modo e distribuire il database e il mirror nello stesso data center. È necessario configurare un database di backup nel data center secondario (con un mirror facoltativo per garantire la disponibilità elevata durante il ripristino di emergenza). Si tratta del database di backup utilizzato per il failover durante il ripristino di emergenza. 
  
Per informazioni dettagliate su come configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente, vedere [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md). 
  
Nelle figure seguenti viene illustrato come configurare il pool di server Chat persistente in due diverse topologie di pool stretch:
  
- Pool di server Persistent Chat esteso quando i data center sono georilevati con un'elevata larghezza di banda e una bassa latenza.
    
- Pool di server Persistent Chat esteso quando i data center sono georilevati con una bassa larghezza di banda e un'elevata latenza.
    
Nella figura 1 viene illustrata una topologia estesa del pool di server Chat persistente in cui i data center sono geolocali con larghezza di banda elevata/bassa latenza. Si supponga che per le topologie logiche e fisiche si presupponga quanto segue:
  
- La topologia logica è costituita dai seguenti elementi:
    
  - Pool di Persistent Chat tra i siti 1 e 2 contenenti server da 1 a 8.
    
  - Un pool Front End Server, un database di Persistent Chat, un database con mirroring e, facoltativamente, un database di controllo (non mostrato nel diagramma) che risiede fisicamente nel sito 1. 
    
  - Un secondo pool Front End Server e un database di backup che risiedono fisicamente nel sito 2.
    
- La topologia fisica è costituita dai siti 1 e 2 come segue:
    
  - Un pool di Persistent Chat, contenente i server da 1 a 4, due attivi, due inattivi nel sito 1.
    
  - Un pool di Persistent Chat, contenente i server da 5 a 8, due attivi, due inattivi nel sito 2.
    
  - Un pool Front End Server, un database di Persistent Chat, un database con mirroring e, facoltativamente, un database di controllo (non illustrato nel diagramma) nel sito 1.
    
  - Un pool Front End Server e un database di backup, che è la destinazione SQL log shipping, nel sito 2.
    
**Pool di server Chat persistente estesa quando i data center si trovano in una posizione geografica con larghezza di banda elevata/bassa latenza**

![Pool di persistent Chat estesa con larghezza di banda elevata/bassa latenza.](../../media/55cf3d4b-5f51-4d2f-84ca-b4a13dc5eba3.png)
  
Nella figura 2 è illustrata una topologia di pool di server Chat persistente estesa in cui i data center sono geolocali con larghezza di banda bassa/latenza elevata.
  
- La topologia logica è costituita dai seguenti elementi:
    
  - Pool di Persistent Chat tra i siti 1 e 2 contenenti server da 1 a 8.
    
  - Un pool Front End Server, un database di Persistent Chat, un database con mirroring e, facoltativamente, un database di controllo (non mostrato nel diagramma) che risiede fisicamente nel sito 1. 
    
  - Un secondo pool Front End Server e un database di backup che risiedono fisicamente nel sito 2.
    
- La topologia fisica è costituita dai siti 1 e 2 come segue:
    
  - Un pool di Persistent Chat, contenente i server da 1 a 4, tutti attivi, nel sito 1.
    
  - Un pool di Persistent Chat, contenente i server da 5 a 8, tutti inattivi, nel sito 2.
    
  - Un pool Front End Server, un database di Persistent Chat, un database con mirroring e, facoltativamente, un database di controllo (non illustrato nel diagramma) nel sito 1.
    
  - Un pool Front End Server e un database di backup, che è la destinazione SQL log shipping, nel sito 2.
    
**Pool di server Chat persistente estesa quando i data center si trovano in una posizione geografica con larghezza di banda bassa/latenza elevata**

![Pool di persistent Chat estesa con larghezza di banda bassa/latenza elevata.](../../media/40cbd902-57b8-4d57-a61c-cde4e0bd47f0.png)
  

