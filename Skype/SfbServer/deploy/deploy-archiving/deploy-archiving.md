---
title: Distribuire l'archiviazione per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50fa535c-7347-4e33-80a3-296748ef6666
description: "Riepilogo: leggere questo argomento per informazioni su come distribuire l'archiviazione per Skype for Business Server."
ms.openlocfilehash: 32b25b373bd5399928d5e5eaed063c194942f697
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825216"
---
# <a name="deploy-archiving-for-skype-for-business-server"></a>Distribuire l'archiviazione per Skype for Business Server
 
**Riepilogo:** Leggere questo argomento per informazioni su come distribuire l'archiviazione per Skype for Business Server.
  
L'archiviazione viene automaticamente installata su ogni Front End Server nella distribuzione di Skype for Business Server, ma è comunque necessario eseguire la procedura iniziale di installazione e configurazione prima di utilizzarla. Prima di iniziare, assicurarsi di avere familiarità con i concetti in [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).
  
## <a name="deployment-checklist"></a>Elenco di controllo di distribuzione

La modalità di configurazione dell'archiviazione dipende dall'opzione di archiviazione scelta: 
  
- Se si utilizza l'integrazione di Microsoft Exchange per tutti gli utenti nella distribuzione, non è necessario configurare i criteri di archiviazione di Skype for Business Server per gli utenti. Invece, si configurano i criteri di Exchange In-Place Hold per supportare l'archiviazione per gli utenti ospitati in Exchange, con le loro cassette postali inserite In-Place blocco. Per informazioni dettagliate sulla configurazione di questi criteri, vedere la documentazione del prodotto Exchange.
    
- Se non si utilizza l'integrazione di Microsoft Exchange per tutti gli utenti nella distribuzione, è necessario aggiungere i database di archiviazione di Skype for Business Server (database di SQL Server) alla topologia, pubblicare la topologia aggiornata e quindi configurare i criteri e le impostazioni di archiviazione per gli utenti. È possibile distribuire i database di archiviazione contemporaneamente alla distribuzione della topologia iniziale o dopo aver distribuito almeno un pool Front end o un server Standard Edition. In questo documento viene descritto come distribuire i database di archiviazione aggiungendoli a una distribuzione esistente.
    
Se si Abilita l'archiviazione in un pool Front end o in un server Standard Edition, è necessario abilitarla per tutti gli altri pool Front end e i server Standard Edition della distribuzione. Questo è dovuto al fatto che gli utenti di cui devono essere archiviate le comunicazioni possono essere invitati a una conversazione di messaggistica istantanea di gruppo oppure a riunioni ospitate in un altro pool. Se l'archiviazione non è abilitata nel pool in cui viene ospitata la conversazione o la riunione, potrebbe non essere possibile archiviare l'intera sessione. In questi casi, è possibile archiviare la messaggistica istantanea con utenti abilitati per l'archiviazione, ma non per file di contenuto delle conferenze e eventi di accesso o abbandono della conferenza.
  
> [!IMPORTANT]
> Se l'archiviazione è critica nell'organizzazione per motivi di conformità, assicurarsi di distribuire l'archiviazione, configurare i criteri e altre opzioni al livello appropriato e quindi attivare l'archiviazione per tutti gli utenti idonei, prima di abilitare tali utenti per Skype for Business Server. 
  
Nella tabella seguente viene fornita una panoramica dei passaggi da eseguire per distribuire l'archiviazione in una topologia esistente.
  
|**Fase**|**Procedura**|**Ruoli e gruppi a cui è necessario appartenere**|**Documentazione**|
|:-----|:-----|:-----|:-----|
|**Installare l'hardware e il software prerequisiti** <br/> |Per utilizzare l'integrazione di Microsoft Exchange (tramite Exchange per l'archiviazione per alcuni o tutti gli utenti), è necessaria una distribuzione di Exchange esistente.  <br/> Per utilizzare database di archiviazione distinti (tramite database di SQL Server) per l'archiviazione di alcuni o di tutti gli utenti, SQL Server nel server in cui verranno archiviati i dati di archiviazione.  <br/> L'archiviazione viene eseguita nei front end server di un pool Enterprise e di server Standard Edition. Non esistono ulteriori requisiti di hardware o software oltre a quelli necessari per l'installazione di questi server.  <br/> |Utente del dominio membro del gruppo Administrators locale  <br/> |[Requisiti del server per Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Requisiti ambientali per Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/>  [Pianificare l'integrazione di Skype for Business ed Exchange](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md) <br/>[Requisiti di sistema per Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md) |
|**Creare la topologia interna appropriata per supportare l'archiviazione (solo se non si utilizza l'integrazione di Microsoft Exchange per tutti gli utenti nella distribuzione)** <br/> |Eseguire Generatore di topologie per aggiungere database di archiviazione di Skype for Business Server (database di SQL Server) alla topologia e quindi pubblicare la topologia.  <br/> |Per definire una topologia per incorporare i database di archiviazione, un account membro del gruppo utenti locali.  <br/> Per pubblicare la topologia, un account che sia membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins e che disponga di autorizzazioni di controllo completo (lettura/scrittura/modifica) sulla condivisione file da utilizzare per l'archivio file di Skype for Business Server, in modo che il generatore di topologie possa configurare gli elenchi DACL necessari.  <br/> |[Aggiungere database di archiviazione a una distribuzione esistente in Skype for Business Server](add-archiving-databases.md) <br/> |
|**Configurare l'autenticazione da server a server (solo se si utilizza l'integrazione di Microsoft Exchange)** <br/> |Configurare i server per l'abilitazione dell'autenticazione tra Skype for Business Server ed Exchange. Prima di abilitare l'archiviazione, è consigliabile eseguire il **dumpster di testuser_sipUri-Folder di test-CsExchangeStorageConnectivity** per convalidare la connettività di archiviazione di Exchange. <br/> |Un account con le autorizzazioni appropriate per la gestione dei certificati sul server.  <br/> |Gestire l'autenticazione da server a server  <br/> |
|**Configurare le opzioni di archiviazione e i criteri** <br/> |Configurare l'archiviazione, tra cui l'integrazione di Microsoft Exchange, il criterio globale e tutti i criteri per i siti e gli utenti (quando non si utilizza l'integrazione di Microsoft Exchange per tutti gli archivi dati) e le opzioni di archiviazione specifiche, ad esempio la modalità critica e l'esportazione ed eliminazione dei dati.  <br/> Se si utilizza l'integrazione di Microsoft Exchange, configurare i criteri di blocco In-Place di Exchange in base alle esigenze.  <br/> |Gruppo RTCUniversalServerAdmins (solo Windows PowerShell) oppure assegnare gli utenti al ruolo CSArchivingAdministrator o CSAdministrator  <br/> |[Configurare le opzioni di archiviazione per Skype for Business Server](configure-archiving-options.md) <br/> Documentazione del prodotto Exchange (se si utilizza l'integrazione di Microsoft Exchange).  <br/> |
   

