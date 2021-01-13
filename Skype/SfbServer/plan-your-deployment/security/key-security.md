---
title: Funzionalità principali di sicurezza in Skype for Business Server
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
ms.collection: IT_Skype16
ms.assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
description: Skype for Business Server include diverse funzionalità di sicurezza, tra cui l'autenticazione da server a server, il controllo di accesso basato sui ruoli e l'archiviazione centralizzata dei dati di configurazione.
ms.openlocfilehash: 1163216f2aeb369576f51af53180297f8028813e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832176"
---
# <a name="key-security-features-in-skype-for-business-server"></a>Funzionalità principali di sicurezza in Skype for Business Server
 
Skype for Business Server include diverse funzionalità di sicurezza, tra cui l'autenticazione da server a server, il controllo di accesso basato sui ruoli e l'archiviazione centralizzata dei dati di configurazione. 
  
In questo articolo viene fornita una panoramica di alto livello sulla sicurezza di Skype for Business Server. 
  
## <a name="key-security-features-in-skype-for-business-server"></a>Funzionalità principali di sicurezza in Skype for Business Server

La sicurezza è un argomento molto ampio. La sicurezza raggiunge tutte le funzionalità di Skype for Business Server, nonché i database, i servizi e i componenti hardware che compongono un ecosistema di Skype for Business Server. In questo articolo vengono illustrate alcune delle funzionalità di Skype for Business Server in particolare progettate per la sicurezza.
  
### <a name="planning-and-design-tools"></a>Strumenti di pianificazione e progettazione

Skype for Business Server offre due strumenti per semplificare la pianificazione e la progettazione e ridurre la possibilità di configurare in modo errato i componenti di Skype for Business Server. 
  
- **Lo strumento di pianificazione della topologia** automatizza gran parte del processo di progettazione della topologia. È possibile esportare i risultati dello strumento di pianificazione in Generatore di topologie, che è lo strumento necessario per installare ogni server che esegue Skype for Business Server.
    
- **Generatore di topologie** archivia tutte le informazioni di configurazione nell'archivio di gestione centrale.
    
Per informazioni dettagliate su questi strumenti, vedere [strumenti di gestione di Skype for Business Server](../../management-tools/management-tools.md).
  
### <a name="central-management-store"></a>Archivio di gestione centrale

In Skype for Business Server, i dati di configurazione relativi ai server e ai servizi fanno parte dell'archivio di gestione centrale. L'archivio di gestione centrale offre un'archiviazione schematizzato e robusta dei dati necessari per definire, configurare, gestire, amministrare, descrivere e gestire una distribuzione di Skype for Business Server. Convalida inoltre i dati per garantire la coerenza della configurazione. Tutte le modifiche apportate ai dati di configurazione si verificano nell'archivio di gestione centrale, eliminando i problemi di "fuori sincrono". 
  
Le copie di sola lettura dei dati sono replicate in tutti i server della topologia, inclusi i server perimetrali e i Survivable Branch Appliance. La replica viene gestita da un servizio eseguito per impostazione predefinita nel contesto del servizio di rete, riducendo i diritti e le autorizzazioni a quelli di un semplice utente nel computer. 
  
### <a name="server-to-server-authentication"></a>Autenticazione da server a server

In Skype for Business Server, l'autenticazione può essere configurata tra i server mediante il protocollo Open Authorization (OAuth). Ad esempio, è possibile configurare Skype for Business Server per l'autenticazione con un server su cui è in esecuzione Microsoft Exchange Server 2016. Se si utilizza il protocollo OAuth, il server Skype for business e il server di Microsoft Exchange possono considerarsi attendibili. Questo fornisce la possibilità di integrare i prodotti in modo semplice. Per informazioni dettagliate, vedere [Manage Server-to-Server Authentication (OAuth) e le applicazioni partner in Skype for Business Server](../../manage/authentication/server-to-server-and-partner-applications.md).
  
### <a name="windows-powershell-based-management-and-web-based-management-interface"></a>Interfaccia di gestione basata su Windows PowerShell e gestione basata sul Web

Skype for Business Server fornisce una potente interfaccia di gestione, basata sull'interfaccia della riga di comando di Windows PowerShell. Questa interfaccia include cmdlet per la gestione della sicurezza e le funzionalità di sicurezza di Windows PowerShell sono abilitate per impostazione predefinita in modo che gli utenti non possano eseguire script facilmente o inconsapevolmente. Ciò significa che le impostazioni predefinite del software sono configurare in modo da ottimizzare automaticamente la sicurezza e ridurre i rischi di attacco. Per informazioni dettagliate sul supporto per la gestione di Windows PowerShell in Skype for Business Server, vedere [Skype for Business Server Management Shell](../../manage/management-shell.md). 
  
### <a name="role-based-access-control-rbac"></a>Controllo di accesso Role-Based (RBAC)

Skype for Business Server fornisce il controllo di accesso basato sui ruoli (RBAC) per consentire di delegare le attività amministrative mantenendo standard elevati per la sicurezza. È possibile utilizzare il controllo di accesso basato sui ruoli per seguire il principio dei privilegi minimi, in base al quale agli utenti vengono concessi solo i diritti amministrativi richiesti dalle loro mansioni. Skype for Business Server offre la possibilità di creare un nuovo ruolo e anche la possibilità di modificare un ruolo esistente. 
  
## <a name="network-address-translation-nat"></a>NAT (Network Address Translation)

Skype for Business Server non supporta l'utilizzo di NAT (Network Address Translation) sull'interfaccia interna del server perimetrale, ma supporta l'inserimento dell'interfaccia esterna del servizio Access Edge, del servizio Web Conferencing Edge e del servizio A/V Edge dietro un router o un firewall che esegue NAT (Network Address Translation) per topologie di server perimetrali consolidate singole e in scala. Più server perimetrali dietro un dispositivo di bilanciamento del carico hardware non possono utilizzare NAT. Se più server perimetrali utilizzano NAT nelle interfacce esterne, è necessario il bilanciamento del carico DNS (Domain Name System). A sua incirca, l'utilizzo del bilanciamento del carico DNS consente di ridurre il numero di indirizzi IP pubblici per ogni server perimetrale in un pool di server perimetrali. Per ulteriori informazioni, vedere [scenari server perimetrali in Skype for Business Server](../../plan-your-deployment/edge-server-deployments/scenarios.md).
  
> [!NOTE]
> Se si esegue la Federazione con le aziende che dispongono di una distribuzione di Microsoft Office Communications Server 2007 ed è necessario utilizzare audio/video tra l'organizzazione e l'organizzazione federata, i requisiti di porta saranno quelli per la versione precedente dei server perimetrali distribuiti. Ad esempio, gli intervalli di porte necessari per le versioni precedenti devono essere aperti per entrambe le aziende finché il partner federato non aggiorna i propri server perimetrali su Skype for Business Server. A quel punto, sarà possibile verificare e ridurre i requisiti delle porte in base alla nuova configurazione. 
  
## <a name="simplified-certificates-for-edge-servers"></a>Certificati semplificati per i server perimetrali

La Distribuzione guidata consente di popolare automaticamente i nomi soggetto (SN) e i nomi soggetto alternativi (SAN) riducendo la possibilità di includere voci superflue e potenzialmente non sicure.
  
## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a>Ciclo di vita dello sviluppo della sicurezza del calcolo Trustworthy (SDL)

Skype for Business Server è stato progettato e sviluppato in conformità con [Microsoft Trustworthy Computing Security Development Lifecycle](https://go.microsoft.com/fwlink/p/?linkid=68761) (SDL).
  
- **Attendibilità per progettazione** Il primo passaggio per la creazione di un sistema di comunicazioni unificate più sicuro consisteva nel progettare modelli di minacce e testare ogni caratteristica come è stato progettato. Microsoft esegue inoltre test al di fuori del comportamento disegnato per individuare vulnerabilità di sicurezza derivanti da comportamenti di prodotto imprevisti. Diversi miglioramenti correlati alla sicurezza sono stati integrati nelle procedure e nel processo di codifica. Gli strumenti in fase di compilazione rilevano i sovraccarichi del buffer e altre potenziali minacce per la sicurezza prima che il codice venga introdotto nel prodotto finale. È ovviamente impossibile progettare un sistema in grado di far fronte a tutte le minacce per la sicurezza sconosciute. Nessun sistema può garantire una completa sicurezza. Tuttavia, poiché lo sviluppo del prodotto ha abbracciato principi di progettazione sicuri fin dall'inizio, Skype for Business Server incorpora tecnologie di sicurezza standard del settore come parte fondamentale della sua architettura.
    
- **Attendibile per impostazione predefinita** Per impostazione predefinita, le comunicazioni di rete in Skype for Business Server sono crittografate. Poiché tutti i server utilizzano i certificati e l'autenticazione Kerberos, TLS, Secure Real-Time Transport Protocol (SRTP) e altre tecniche di crittografia standard del settore, tra cui la crittografia AES (Advanced Encryption Standard) di 128 bit, praticamente tutti i dati di Skype for Business Server sono protetti in rete. Inoltre, il controllo di accesso basato sui ruoli rende possibile la distribuzione dei server che eseguono Skype for Business Server in modo che ogni ruolo del server esegua solo i servizi e disponga solo delle autorizzazioni relative a tali servizi, appropriate per il ruolo del server.
    
- **Attendibilità mediante la distribuzione** Tutta la documentazione di Skype for Business Server include procedure consigliate e consigli utili per determinare e configurare i livelli di sicurezza ottimali per la distribuzione e valutare i rischi di sicurezza per l'attivazione di opzioni non predefinite.
    

