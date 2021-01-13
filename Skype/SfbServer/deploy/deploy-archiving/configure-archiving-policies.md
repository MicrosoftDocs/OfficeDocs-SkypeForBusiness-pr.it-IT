---
title: Configurazione dei criteri di archiviazione per Skype for Business Server
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
ms.assetid: e8e48087-d4f0-4fe1-9e7e-f2b3e07f815f
description: 'Riepilogo: leggere questo argomento per informazioni su come configurare i criteri di archiviazione iniziali per gli utenti di Skype for Business Server.'
ms.openlocfilehash: ab737305561aa20c873bbce6e0f075d17fedd0d6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820856"
---
# <a name="configure-archiving-policies-for-skype-for-business-server"></a>Configurazione dei criteri di archiviazione per Skype for Business Server
 
**Riepilogo:** Leggere questo argomento per informazioni su come configurare i criteri di archiviazione iniziali per gli utenti di Skype for Business Server.
  
In Skype for Business Server, è possibile utilizzare i criteri per abilitare e disabilitare l'archiviazione delle comunicazioni interne e delle comunicazioni esterne per gli utenti che si trovano in Skype for Business Server. Sono incluse le attività seguenti:
  
- Un criterio globale creato per impostazione predefinita quando si distribuisce Skype for Business Server
    
- Criteri facoltativi a livello di sito che specificano la modalità di implementazione dell'archiviazione per un sito specifico
    
- Criteri facoltativi a livello di utente che specificano la modalità di implementazione dell'archiviazione per utenti specifici
    
Inizialmente sono stati configurati i criteri di archiviazione quando si distribuisce l'archiviazione, ma è possibile modificare, aggiungere ed eliminare criteri dopo la distribuzione. Nel pannello di controllo di Skype for Business Server, è possibile utilizzare la pagina **criteri di archiviazione** del gruppo di **archiviazione e monitoraggio** per gestire i criteri a livello globale, di sito e di utente.
  
> [!NOTE]
> Per controllare l'implementazione dell'archiviazione, è necessario specificare le opzioni, ad esempio se archiviare la messaggistica istantanea o le conferenze, l'utilizzo della modalità critica e le opzioni di eliminazione. Per impostazione predefinita, nessuna opzione è abilitata nella configurazione di archiviazione globale o in qualsiasi configurazione di archiviazione del sito o del pool. Prima di abilitare l'archiviazione per le comunicazioni interne o esterne, è necessario specificare tutte le opzioni appropriate. Per ulteriori informazioni, vedere [configurare le opzioni di archiviazione per Skype for Business Server](configure-archiving-options.md). 
  
> [!NOTE]
> Se si Abilita l'integrazione di Microsoft Exchange per la distribuzione, i criteri di Exchange In-Place conservazione determinano se l'archiviazione è abilitata per gli utenti ospitati in Exchange e le cassette postali vengono inserite In-Place blocco. 
  
Per informazioni dettagliate sul funzionamento dei criteri di archiviazione, inclusa la gerarchia per i criteri globali, del sito e degli utenti, vedere [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md). Per informazioni dettagliate su come gestire i criteri dopo la distribuzione, vedere [gestire i criteri di archiviazione in Skype for Business Server](../../manage/archiving/policies.md).
  
## <a name="global-policy"></a>Criterio globale

Quando si distribuisce i Front End Server, in Skype for Business Server viene creato un criterio globale per l'archiviazione. Per impostazione predefinita, l'archiviazione è disabilitata nei criteri globali. Il criterio globale determina se l'archiviazione è abilitata per le comunicazioni interne ed esterne per l'intera distribuzione, a meno che non si configurano i criteri di sito o utente, che sostituiscono il criterio globale, o se si utilizza l'integrazione di Microsoft Exchange per alcuni o tutti gli utenti. Se si utilizza l'integrazione di Microsoft Exchange, il criterio globale non si applica a tutti gli utenti ospitati in Exchange e le cassette postali vengono inserite In-Place blocco.
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a>Configurazione dei criteri globali per l'archiviazione dei database di archiviazione di Skype for Business Server

1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server. 
    
3. Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Criteri di archiviazione**.
    
4. Nella pagina **Criteri di archiviazione** fare clic su **Globale**, **Modifica** e quindi su **Mostra dettagli**.
    
5. In **Modifica Criteri di archiviazione - Globale** eseguire le operazioni seguenti:
    
   - In **Nome**, se non si vuole usare il nome predefinito Globale, specificare un nuovo nome per i criteri globali. 
    
   - In **Descrizione** fornire informazioni sui criteri, ad esempio i criteri globali per  *divisionname*  .
    
   - Per controllare l'archiviazione delle comunicazioni interne per tutti i siti e gli utenti non controllati in modo specifico tramite criteri utente o sito, selezionare o deselezionare la casella di controllo **Archivia comunicazioni interne**.
    
   - Per controllare l'archiviazione delle comunicazioni esterne per tutti i siti e gli utenti non controllati in modo specifico tramite criteri utente o di sito, selezionare o deselezionare la casella di controllo **Archivia comunicazioni esterne**.
    
6. Fare clic su **Commit**.
    
## <a name="site-policies"></a>Criteri sito

È possibile abilitare o disabilitare l'archiviazione per siti specifici creando un criterio di archiviazione per ognuno di questi siti. Un criterio sito ha la precedenza sui criteri globali, ma i criteri degli utenti eseguono l'override dei criteri sito. I criteri di archiviazione si applicano solo se non si utilizza l'integrazione di Microsoft Exchange o, se si utilizza l'integrazione di Microsoft Exchange, ma alcuni utenti non sono ospitati in Exchange e le relative cassette postali vengono inserite In-Place.
  
### <a name="create-an-archiving-policy-for-a-site"></a>Creare un criterio di archiviazione per un sito

1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server.
    
3. Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Criteri di archiviazione**.
    
    Per informazioni dettagliate sul funzionamento dei criteri di archiviazione, inclusa la gerarchia per i criteri globali, del sito e degli utenti, vedere [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).
    
4. Fare clic su **Nuovo** e quindi su **Criteri sito**.
    
5. In **Seleziona un sito** fare clic sul sito a cui devono essere applicati i criteri.
    
6. In **Crea nuovi criteri di archiviazione** eseguire le operazioni seguenti:
    
   - In **nome** specificare il nome del criterio sito. 
    
   - In **Descrizione** fornire informazioni sui criteri di sito, ad esempio criteri sito per Redmond.
    
   - Per controllare l'archiviazione delle comunicazioni interne per il sito specificato, selezionare o deselezionare la casella di controllo **Archivia comunicazioni interne** .
    
   - Per controllare l'archiviazione delle comunicazioni esterne per il sito specificato, selezionare o deselezionare la casella di controllo **Archivia comunicazioni esterne** .
    
7. Fare clic su **Commit**.
    
## <a name="user-policies"></a>Criteri utente

È possibile abilitare o disabilitare l'archiviazione per utenti specifici mediante la creazione e la configurazione di un criterio di archiviazione per gli utenti e quindi l'applicazione del criterio a utenti o gruppi utente specifici. I criteri utente sostituiscono eventuali criteri globali o sito. I criteri di archiviazione si applicano solo se non si utilizza l'integrazione di Microsoft Exchange o, se si utilizza l'integrazione di Microsoft Exchange, ma alcuni utenti non sono ospitati in Exchange e le relative cassette postali vengono inserite In-Place.
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a>Configurare un criterio di archiviazione per gli utenti ospitati in Skype for Business Server

1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server. 
    
3. Nella barra di spostamento sinistra fare clic su **Monitoraggio e archiviazione** e quindi su **Criteri di archiviazione**.
    
4. Fare clic su **Nuovo** e quindi su **Criteri utente**.
    
5. In **Nuovi criteri di archiviazione** eseguire le operazioni seguenti:
    
   - In **Nome** specificare un nome per i criteri utente. 
    
   - In **Descrizione** immettere informazioni sugli scopi dei criteri utente, ad esempio "Criteri utente per il reparto legale".
    
   - Per controllare l'archiviazione delle comunicazioni interne per i criteri utente, selezionare o deselezionare la casella di controllo **Archivia comunicazioni interne**.
    
   - Per controllare l'archiviazione delle comunicazioni esterne per i criteri utente, selezionare o deselezionare la casella di controllo **Archivia comunicazioni esterne**.
    
6. Fare clic su **Commit**.
    
I criteri utente si applicano solo agli utenti a cui vengono assegnati.
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a>Applicare un criterio di archiviazione di Skype for Business Server a un utente

1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server. 
    
3. Sulla barra di spostamento sinistra fare clic su **Utenti** e quindi cercare l'account utente che si desidera configurare.
    
4. Nella tabella dei risultati di ricerca fare clic sull'account utente, fare clic su **Modifica** e quindi fare clic su **Mostra dettagli**.
    
5. In **modifica utente di Skype for Business Server** in **criteri di archiviazione**, selezionare i criteri utente di archiviazione che si desidera applicare.
    
    > [!NOTE]
    > Le **\<Automatic\>** impostazioni applicano le impostazioni di installazione predefinite del server. Queste impostazioni vengono applicate automaticamente dal server.
  
6. Fare clic su **Commit**.
    

