---
title: Configurare i criteri di archiviazione per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8e48087-d4f0-4fe1-9e7e-f2b3e07f815f
description: 'Riepilogo: leggere questo argomento per informazioni su come configurare i criteri di archiviazione iniziali per gli utenti di Skype for Business Server.'
ms.openlocfilehash: 4e1bf5d713201604df18db9d63c2057bfa5bb4e8
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234552"
---
# <a name="configure-archiving-policies-for-skype-for-business-server"></a>Configurare i criteri di archiviazione per Skype for Business Server
 
**Riepilogo:** Leggere questo argomento per informazioni su come configurare i criteri di archiviazione iniziali per gli utenti di Skype for Business Server.
  
In Skype for Business Server si usano i criteri per abilitare e disabilitare l'archiviazione per comunicazioni interne e comunicazioni esterne per gli utenti residenti in Skype for Business Server. Sono inclusi i seguenti:
  
- Un criterio globale creato per impostazione predefinita quando si distribuisce Skype for Business Server
    
- Criteri facoltativi a livello di sito che specificano la modalità di implementazione dell'archiviazione per un sito specifico
    
- Criteri facoltativi a livello utente che specificano la modalità di implementazione dell'archiviazione per utenti specifici
    
I criteri di archiviazione sono stati inizialmente impostati quando si distribuisce l'archiviazione, ma è possibile modificare, aggiungere ed eliminare criteri dopo la distribuzione. Nel pannello di controllo di Skype for Business Server è possibile usare la pagina **criteri di archiviazione** del gruppo **archiviazione e monitoraggio** per gestire i criteri a livello globale, del sito e degli utenti.
  
> [!NOTE]
> Per controllare l'implementazione dell'archiviazione, è necessario specificare le opzioni, ad esempio l'archiviazione di messaggi istantanei o di conferenza, l'uso delle opzioni di modalità critiche ed eliminazione. Per impostazione predefinita, nessuna opzione è abilitata nella configurazione di archiviazione globale o in qualsiasi configurazione di archiviazione di siti o pool. Devi specificare tutte le opzioni appropriate prima di abilitare l'archiviazione per comunicazioni interne o esterne. Per informazioni dettagliate, vedere [configurare le opzioni di archiviazione per Skype for Business Server](configure-archiving-options.md). 
  
> [!NOTE]
> Se si Abilita l'integrazione di Microsoft Exchange per la distribuzione, i criteri di blocco sul posto di Exchange controllano se l'archiviazione è abilitata per gli utenti ospitati in Exchange e le cassette postali vengono messe sul posto. 
  
Per informazioni dettagliate sul funzionamento dei criteri di archiviazione, ad esempio la gerarchia per i criteri globali, per il sito e per gli utenti, vedere [pianificare l'archiviazione in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md). Per informazioni dettagliate su come gestire i criteri dopo la distribuzione, vedere [gestire i criteri di archiviazione in Skype for Business Server](../../manage/archiving/policies.md).
  
## <a name="global-policy"></a>Criterio globale

Quando si distribuiscono i server front-end, Skype for Business Server crea un criterio globale per l'archiviazione. Per impostazione predefinita, l'archiviazione è disabilitata nel criterio globale. Il criterio globale controlla se l'archiviazione è abilitata per le comunicazioni interne ed esterne per l'intera distribuzione, a meno che non vengano configurati i criteri del sito o degli utenti, che eseguono l'override del criterio globale o se si usa l'integrazione di Microsoft Exchange per alcuni o tutti Gli utenti. Se si usa l'integrazione di Microsoft Exchange, il criterio globale non si applica agli utenti ospitati in Exchange e hanno inserito le cassette postali sul posto.
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a>Configurare i criteri globali per l'archiviazione per i database di archiviazione di Skype for Business Server

1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 
    
3. Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **criteri di archiviazione**.
    
4. Nella pagina **criteri di archiviazione** fare clic su **globale**, fare clic su **modifica**e quindi su **Mostra dettagli**.
    
5. In **modifica criteri di archiviazione-globale**eseguire le operazioni seguenti:
    
   - In **nome**, se non si vuole usare il nome predefinito globale, specificare un nuovo nome per il criterio globale. 
    
   - In **Descrizione**, fornisci informazioni sui criteri, ad esempio i criteri globali per divisioname ** .
    
   - Per controllare l'archiviazione delle comunicazioni interne per tutti i siti e gli utenti non controllati in modo specifico tramite criteri del sito o criteri utente, selezionare o deselezionare la casella di controllo **Archivia comunicazioni interne** .
    
   - Per controllare l'archiviazione delle comunicazioni esterne per tutti i siti e gli utenti non controllati in modo specifico tramite criteri del sito o criteri utente, selezionare o deselezionare la casella di controllo **Archivia comunicazioni esterne** .
    
6. Fare clic su **Commit**.
    
## <a name="site-policies"></a>Criteri sito

È possibile abilitare o disabilitare l'archiviazione per siti specifici creando un criterio di archiviazione per ognuno di questi siti. Un criterio di sito sostituisce il criterio globale, ma i criteri utente sostituiscono i criteri del sito. I criteri di archiviazione si applicano solo se non si usa l'integrazione di Microsoft Exchange o, se si usa l'integrazione di Microsoft Exchange, ma alcuni utenti non sono ospitati in Exchange e le cassette postali vengono inserite in un blocco sul posto.
  
### <a name="create-an-archiving-policy-for-a-site"></a>Creare un criterio di archiviazione per un sito

1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **criteri di archiviazione**.
    
    Per informazioni dettagliate sul funzionamento dei criteri di archiviazione, ad esempio la gerarchia per i criteri globali, per il sito e per gli utenti, vedere [pianificare l'archiviazione in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).
    
4. Fare clic su **Nuovo** e quindi su **Criteri sito**.
    
5. In **Seleziona un sito**fare clic sul sito a cui applicare il criterio.
    
6. In **nuovi criteri di archiviazione**eseguire le operazioni seguenti:
    
   - In **nome**specificare il nome per il criterio del sito. 
    
   - In **Descrizione**immettere informazioni sui criteri del sito, ad esempio i criteri del sito per Redmond.
    
   - Per controllare l'archiviazione delle comunicazioni interne per il sito specificato, selezionare o deselezionare la casella di controllo **Archivia comunicazioni interne** .
    
   - Per controllare l'archiviazione delle comunicazioni esterne per il sito specificato, selezionare o deselezionare la casella di controllo **Archivia comunicazioni esterne** .
    
7. Fare clic su **Commit**.
    
## <a name="user-policies"></a>Criteri per gli utenti

È possibile abilitare o disabilitare l'archiviazione per utenti specifici creando e configurando un criterio di archiviazione per gli utenti e quindi applicando il criterio a utenti o gruppi utente specifici. I criteri utente eseguono l'override di qualsiasi criterio globale o dei criteri del sito. I criteri di archiviazione si applicano solo se non si usa l'integrazione di Microsoft Exchange o, se si usa l'integrazione di Microsoft Exchange, ma alcuni utenti non sono ospitati in Exchange e le cassette postali vengono inserite in un blocco sul posto.
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a>Configurare un criterio di archiviazione per gli utenti ospitati in Skype for Business Server

1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 
    
3. Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **criteri di archiviazione**.
    
4. Fare clic su **Nuovo** e quindi su **Criteri utente**.
    
5. In **nuovi criteri di archiviazione**eseguire le operazioni seguenti:
    
   - In **nome**specificare il nome per il criterio utente. 
    
   - In **Descrizione**, fornisci informazioni sui criteri utente (ad esempio, criteri utente per il reparto legale).
    
   - Per controllare l'archiviazione delle comunicazioni interne per i criteri utente, selezionare o deselezionare la casella di controllo **Archivia comunicazioni interne** .
    
   - Per controllare l'archiviazione delle comunicazioni esterne per i criteri utente, selezionare o deselezionare la casella di controllo **Archivia comunicazioni esterne** .
    
6. Fare clic su **Commit**.
    
Un criterio utente si applica solo agli utenti a cui si assegnano i criteri.
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a>Applicare un criterio di archiviazione di Skype for Business Server a un utente

1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 
    
3. Nella barra di spostamento sinistra fare clic su **utenti**e quindi cercare l'account utente che si vuole configurare.
    
4. Nella tabella in cui sono elencati i risultati della ricerca fare clic sull'account utente, su **Modifica** e quindi su **Mostra dettagli**.
    
5. In **modifica utenti di Skype for Business Server** in **criteri di archiviazione**Selezionare i criteri utente di archiviazione che si desidera applicare.
    
    > [!NOTE]
    > Le ** \<impostazioni\> automatiche** applicano le impostazioni di installazione del server predefinite. Queste impostazioni vengono applicate automaticamente dal server.
  
6. Fare clic su **Commit**.
    

