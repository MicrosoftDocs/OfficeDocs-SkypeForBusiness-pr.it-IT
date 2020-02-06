---
title: Caratteristiche di sicurezza chiave in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
description: Skype for Business Server include diverse funzionalità di sicurezza, tra cui l'autenticazione da server a server, il controllo dell'accesso basato sui ruoli e lo spazio di archiviazione centralizzato dei dati di configurazione.
ms.openlocfilehash: ac1891194d231c4d494ba4014e4abd8bd7f1185b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815654"
---
# <a name="key-security-features-in-skype-for-business-server"></a>Caratteristiche di sicurezza chiave in Skype for Business Server
 
Skype for Business Server include diverse funzionalità di sicurezza, tra cui l'autenticazione da server a server, il controllo dell'accesso basato sui ruoli e lo spazio di archiviazione centralizzato dei dati di configurazione. 
  
Questo articolo offre una panoramica di alto livello sulla sicurezza di Skype for Business Server. 
  
## <a name="key-security-features-in-skype-for-business-server"></a>Caratteristiche di sicurezza chiave in Skype for Business Server

La sicurezza è un argomento molto ampio. La sicurezza raggiunge tutte le funzionalità di Skype for Business Server, nonché database, servizi e hardware che costituiscono un ecosistema di Skype for Business Server. In questo articolo vengono illustrate alcune delle funzionalità di Skype for Business Server, in particolare progettate per la sicurezza.
  
### <a name="planning-and-design-tools"></a>Strumenti di pianificazione e progettazione

Skype for Business Server offre due strumenti per facilitare la pianificazione e la progettazione e per ridurre la possibilità di configurare in modo errato i componenti di Skype for Business Server. 
  
- **Lo strumento di pianificazione della topologia** automatizza gran parte del processo di progettazione della topologia. È possibile esportare i risultati dello strumento di pianificazione in Generatore di topologia, che è lo strumento necessario per installare ogni server che utilizza Skype for Business Server.
    
- **Generatore di topologie** archivia tutte le informazioni di configurazione nell'Central Management store.
    
Per informazioni dettagliate su questi strumenti, Vedi [strumenti di gestione di Skype for Business Server](../../management-tools/management-tools.md).
  
### <a name="central-management-store"></a>Central Management store

In Skype for Business Server i dati di configurazione relativi a server e servizi fanno parte di Central Management store. Central Management store offre uno spazio di archiviazione robusto e schematizzato dei dati necessari per definire, configurare, gestire, amministrare, descrivere e gestire una distribuzione di Skype for Business Server. Convalida inoltre i dati per garantire la coerenza della configurazione. Tutte le modifiche apportate ai dati di configurazione si verificano presso l'Central Management store, eliminando i problemi di "fuori sincrono". 
  
Le copie di sola lettura dei dati vengono replicate in tutti i server della topologia, inclusi Edge Server e Survivable Branch Appliance. La replica è gestita da un servizio che, per impostazione predefinita, viene eseguito nel contesto del servizio di rete, riducendo i diritti e le autorizzazioni a quello di un utente semplice nel computer. 
  
### <a name="server-to-server-authentication"></a>Autenticazione da server a server

In Skype for Business Server l'autenticazione può essere configurata tra i server tramite il protocollo OAuth (Open Authorization). Ad esempio, puoi configurare Skype for Business Server per l'autenticazione con un server che sta usando Microsoft Exchange Server 2016. Usando il protocollo OAuth, il server Skype for business e il server di Microsoft Exchange possono considerarsi attendibili. Questo consente di integrare i prodotti in modo uniforme. Per informazioni dettagliate, vedere [gestire l'autenticazione da server a server (OAuth) e le applicazioni partner in Skype for Business Server](../../manage/authentication/server-to-server-and-partner-applications.md).
  
### <a name="windows-powershell-based-management-and-web-based-management-interface"></a>Interfaccia di gestione basata su Windows PowerShell e gestione basata sul Web

Skype for Business Server offre una potente interfaccia di gestione, basata sull'interfaccia della riga di comando di Windows PowerShell. Include i cmdlet per la gestione della sicurezza e le funzionalità di sicurezza di Windows PowerShell sono abilitate per impostazione predefinita in modo che gli utenti non possano eseguire facilmente o inconsapevolmente gli script. Questo significa che le impostazioni predefinite del software sono impostate in modo da aiutare automaticamente a massimizzare la sicurezza e ridurre i viali di attacco. Per informazioni dettagliate sul supporto per la gestione di Windows PowerShell in Skype for Business Server, vedere [Skype for Business Server Management Shell](../../manage/management-shell.md). 
  
### <a name="role-based-access-control-rbac"></a>Controllo di accesso basato sui ruoli (RBAC)

Skype for Business Server fornisce il controllo di accesso basato sui ruoli (RBAC) per consentire di delegare le attività amministrative mantenendo standard elevati per la sicurezza. È possibile usare RBAC per seguire il principio "privilegio minimo", in cui agli utenti vengono assegnati solo i diritti amministrativi necessari per i processi. Skype for Business Server offre la possibilità di creare un nuovo ruolo e anche la possibilità di modificare un ruolo esistente. 
  
## <a name="network-address-translation-nat"></a>NAT (Network Address Translation)

Skype for Business Server non supporta l'uso di NAT (Network Address Translation) nell'interfaccia interna di Edge Server, ma supporta l'inserimento dell'interfaccia esterna di Access Edge service, Web Conferencing Edge service e A/V Edge service dietro un router o un firewall che esegue la traduzione di indirizzi di rete per le topologie di server perimetrale consolidate singole e in scala. Più Edge Server dietro un bilanciamento del carico hardware non può usare NAT. Se più Edge Server usano NAT sulle loro interfacce esterne, è necessario il bilanciamento del carico DNS (Domain Name System). A sua volta, l'uso del bilanciamento del carico DNS consente di ridurre il numero di indirizzi IP pubblici per ogni server perimetrale in un pool di Edge Server. Per informazioni dettagliate, vedere [scenari di Edge Server in Skype for Business Server](../../plan-your-deployment/edge-server-deployments/scenarios.md).
  
> [!NOTE]
> Se si esegue la Federazione con le aziende che hanno una distribuzione di Microsoft Office Communications Server 2007 ed è necessario usare audio/video tra l'organizzazione e l'organizzazione federata, i requisiti della porta saranno quelli della versione precedente di Edge Server distribuiti. Ad esempio, gli intervalli di porta necessari per le versioni meno recenti devono essere aperti per entrambe le aziende fino a quando il partner federativo non aggiorna i propri Edge Server in Skype for Business Server. A questo punto, i requisiti della porta possono essere rivisti e ridotti in base alla nuova configurazione. 
  
## <a name="simplified-certificates-for-edge-servers"></a>Certificati semplificati per Edge Server

La distribuzione guidata può automaticamente popolare i nomi dei soggetti (SNs) e i nomi alternativi oggetto (SANs), riducendo la possibilità di includere voci non necessarie e potenzialmente non sicure.
  
## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a>Ciclo di vita per lo sviluppo della sicurezza (SDL) Trustworthy Computing

Skype for Business Server è progettato e sviluppato in conformità con il processo SDL ( [Microsoft Trustworthy Computing Security Development Lifecycle](https://go.microsoft.com/fwlink/p/?linkid=68761) ).
  
- **Attendibile per progettazione** Il primo passaggio per creare un sistema di comunicazioni unificate più sicuro consiste nel progettare modelli di minacce e testare ogni funzionalità come è stata progettata. Microsoft esegue inoltre test al di fuori del comportamento progettato per individuare le vulnerabilità di sicurezza derivanti da un comportamento del prodotto imprevisto. Diversi miglioramenti relativi alla sicurezza sono stati integrati nel processo e nelle pratiche di codifica. Gli strumenti della fase di compilazione rilevano sovraccarichi del buffer e altre potenziali minacce alla sicurezza prima che il codice venga archiviato nel prodotto finale. Ovviamente, è impossibile progettare contro tutte le minacce alla sicurezza sconosciute. Nessun sistema può garantire una protezione completa. Tuttavia, poiché lo sviluppo del prodotto ha abbracciato i principi di progettazione sicuri fin dall'inizio, Skype for Business Server incorpora tecnologie di sicurezza standard del settore come parte fondamentale della sua architettura.
    
- **Attendibile per impostazione predefinita** Per impostazione predefinita, le comunicazioni di rete in Skype for Business Server sono crittografate. Poiché tutti i server usano i certificati e l'autenticazione Kerberos, TLS, Secure Real-Time Transport Protocol (SRTP) e altre tecniche di crittografia standard del settore, tra cui la crittografia AES (Advanced Encryption Standard) di 128 bit, praticamente tutti i tipi di Skype for I dati di Business Server sono protetti in rete. Inoltre, il controllo dell'accesso basato sui ruoli consente di distribuire server che usano Skype for Business Server in modo che ogni ruolo del server esegua solo i servizi e disponga solo delle autorizzazioni correlate a tali servizi, che sono appropriate per il ruolo del server.
    
- **Attendibile per distribuzione** Tutta la documentazione di Skype for Business Server include procedure consigliate e consigli utili per determinare e configurare i livelli di sicurezza ottimali per la distribuzione e valutare i rischi di sicurezza per l'attivazione delle opzioni non predefinite.
    

