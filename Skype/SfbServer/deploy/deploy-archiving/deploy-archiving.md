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
ms.localizationpriority: medium
ms.assetid: 50fa535c-7347-4e33-80a3-296748ef6666
description: "Riepilogo: leggere questo argomento per informazioni su come distribuire l'archiviazione per Skype for Business Server."
ms.openlocfilehash: 405946cb863c72399115b869f33bf8d107cec455
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58606575"
---
# <a name="deploy-archiving-for-skype-for-business-server"></a>Distribuire l'archiviazione per Skype for Business Server
 
**Riepilogo:** Leggere questo argomento per informazioni su come distribuire l'archiviazione per Skype for Business Server.
  
L'archiviazione viene installata automaticamente in ogni Front End Server della distribuzione di Skype for Business Server, ma è comunque necessario eseguire i passaggi di configurazione e configurazione iniziali prima di poterlo utilizzare. Prima di iniziare, assicurarsi di avere familiarità con i concetti descritti in [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).
  
## <a name="deployment-checklist"></a>Elenco di controllo per la distribuzione

La modalità di configurazione dell'archiviazione dipende dall'opzione di archiviazione scelta: 
  
- Se si utilizza l'integrazione di Microsoft Exchange per tutti gli utenti della distribuzione, non è necessario configurare i criteri di Skype for Business Server di archiviazione per gli utenti. È invece possibile configurare i Exchange In-Place di archiviazione per supportare l'archiviazione per gli utenti ospitati in Exchange, con le cassette postali In-Place conservazione. Per informazioni dettagliate sulla configurazione di questi criteri, vedere la documentazione Exchange prodotto.
    
- Se non si utilizza l'integrazione di Microsoft Exchange per tutti gli utenti della distribuzione, è necessario aggiungere database di archiviazione Skype for Business Server (database SQL Server) alla topologia, pubblicare la topologia aggiornata e quindi configurare i criteri e le impostazioni di archiviazione per gli utenti. È possibile distribuire i database di archiviazione contemporaneamente alla distribuzione della topologia iniziale o dopo aver distribuito almeno un pool Front End o un edizione Standard Server. In questo documento viene descritto come distribuire i database di archiviazione aggiungendoli a una distribuzione esistente.
    
Se si abilita l'archiviazione in un pool Front End o edizione Standard Server, è consigliabile abilitarla per tutti gli altri pool Front End e edizione Standard Server nella distribuzione. Questo è dovuto al fatto che gli utenti di cui devono essere archiviate le comunicazioni possono essere invitati a una conversazione di messaggistica istantanea di gruppo oppure a riunioni ospitate in un altro pool. Se l'archiviazione non è abilitata nel pool in cui viene ospitata la conversazione o la riunione, potrebbe non essere possibile archiviare l'intera sessione. In questi casi, è possibile archiviare la messaggistica istantanea con utenti abilitati per l'archiviazione, ma non per file di contenuto delle conferenze e eventi di accesso o abbandono della conferenza.
  
> [!IMPORTANT]
> Se l'archiviazione è fondamentale nell'organizzazione per motivi di conformità, assicurarsi di distribuire l'archiviazione, configurare criteri e altre opzioni al livello appropriato e quindi attivare l'archiviazione per tutti gli utenti appropriati, prima di abilitare tali utenti per Skype for Business Server. 
  
Nella tabella seguente viene fornita una panoramica dei passaggi da eseguire per distribuire l'archiviazione in una topologia esistente.
  
|**Fase**|**Procedura**|**Ruoli e gruppi a cui è necessario appartenere**|**Documentazione**|
|:-----|:-----|:-----|:-----|
|**Installare l'hardware e il software prerequisiti** <br/> |Per usare l'integrazione di Microsoft Exchange (usando Exchange per l'archiviazione per alcuni o tutti gli utenti), è necessaria una distribuzione Exchange esistente.  <br/> Per utilizzare database di archiviazione separati (utilizzando SQL Server database di archiviazione) per l'archiviazione per alcuni o tutti gli utenti, SQL Server nel server in cui verranno archiviati i dati di archiviazione.  <br/> L'archiviazione viene eseguita nei Front End Server di un pool Enterprise e edizione Standard Server. Non esistono ulteriori requisiti di hardware o software oltre a quelli necessari per l'installazione di questi server.  <br/> |Utente del dominio membro del gruppo Administrators locale  <br/> |[Requisiti del server per Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Requisiti ambientali per Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/>  [Pianificare l'integrazione di Skype for Business ed Exchange](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md) <br/>[Requisiti di sistema per Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md) |
|**Creare la topologia interna appropriata per supportare l'archiviazione (solo se non si utilizza l'integrazione di Microsoft Exchange per tutti gli utenti della distribuzione)** <br/> |Eseguire Generatore di topologie per aggiungere Skype for Business Server database di archiviazione (SQL Server database) alla topologia e quindi pubblicare la topologia.  <br/> |Per definire una topologia per incorporare database di archiviazione, un account membro del gruppo di utenti locale.  <br/> Per pubblicare la topologia, un account membro del gruppo domain admins e RTCUniversalServerAdmins e che dispone delle autorizzazioni di controllo completo (lettura/scrittura/modifica) per la condivisione file da utilizzare per l'archivio file di Skype for Business Server (in modo che Generatore di topologie possa configurare i DACL necessari).  <br/> |[Aggiungere database di archiviazione a una distribuzione esistente in Skype for Business Server](add-archiving-databases.md) <br/> |
|**Configurare l'autenticazione da server a server (solo se si utilizza l'integrazione Exchange Microsoft)** <br/> |Configurare i server per abilitare l'autenticazione tra Skype for Business Server e Exchange. È consigliabile eseguire **Test-CsExchangeStorageConnectivity testuser_sipUri -Folder Dumpster** per convalidare Exchange di archiviazione prima di abilitare l'archiviazione. <br/> |Un account con le autorizzazioni appropriate per la gestione dei certificati sul server.  <br/> |Gestire l'autenticazione da server a server  <br/> |
|**Configurare le opzioni e i criteri di archiviazione** <br/> |Configurare l'archiviazione, incluso se utilizzare l'integrazione di Microsoft Exchange, i criteri globali e i criteri sito e utente (quando non si utilizza l'integrazione di Microsoft Exchange per tutta l'archiviazione dei dati) e opzioni di archiviazione specifiche, ad esempio la modalità critica, l'esportazione e l'eliminazione dei dati.  <br/> Se si usa l'integrazione Exchange Microsoft, configurare i criteri Exchange In-Place di blocco in base alle esigenze.  <br/> |Gruppo RTCUniversalServerAdmins (solo Windows PowerShell) oppure assegnare gli utenti al ruolo CSArchivingAdministrator o CSAdministrator  <br/> |[Configurare le opzioni di archiviazione per Skype for Business Server](configure-archiving-options.md) <br/> Exchange documentazione del prodotto (se si utilizza l'integrazione Exchange Microsoft).  <br/> |
   

