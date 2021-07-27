---
title: Rimozione delle autorizzazioni Skype for Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Istruzioni per la rimozione delle autorizzazioni Skype for Business Server.
ms.openlocfilehash: bdd38578d8ee98c26e6515c1cd4baa0ef8a825cf
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2021
ms.locfileid: "53510787"
---
# <a name="remove-your-on-premises-skype-for-business-deployment"></a>Rimuovere la distribuzione locale di Skype for Business

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

In questo articolo viene descritto come rimuovere la distribuzione locale Skype for Business locale. Questo è il passaggio 4 della procedura seguente per rimuovere le autorizzazioni dell'ambiente locale:

- Passaggio 1. [Spostare tutti gli utenti necessari da locale a online.](decommission-move-on-prem-users.md) 

- Passaggio 2. [Disabilitare la configurazione ibrida](cloud-consolidation-disabling-hybrid.md).

- Passaggio 3. [Eseguire la migrazione di endpoint di applicazioni ibride da locale a online](decommission-move-on-prem-endpoints.md)

- **Passaggio 4. Rimuovere la distribuzione locale Skype for Business locale.** (Questo articolo)


> [!IMPORTANT] 
> La procedura descritta in questo articolo si applica solo se si utilizza il metodo 2 per la gestione degli attributi utente, come descritto [qui.](cloud-consolidation-managing-attributes.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory) Se si utilizza il metodo 1, non eseguire la procedura descritta in questo articolo per rimuovere i Skype for Business server. Al contrario, è possibile ri-immagine dei server.

Per completare i passaggi descritti in questo articolo, sono necessari privilegi sia per il gruppo Schema Admins che per il Enterprise Admin. Questi privilegi sono necessari per annullare le modifiche Skype for Business Server schema e a livello di foresta in Servizi di dominio Active Directory. Sarà inoltre necessario essere membri del gruppo RTCUniversalServerAdmins.


## <a name="prepare-to-remove-the-skype-for-business-deployment"></a>Preparare la rimozione della Skype for Business distribuzione

Dopo aver spostato tutti gli account utente necessari nel cloud, potrebbero essere ancora presenti alcuni oggetti locali rimanenti, ad esempio contatti e applicazioni, che sarà necessario pulire.

Eseguire la procedura seguente per pulire questi oggetti e assicurarsi di essere membri sia del gruppo Amministratore locale che del gruppo RTCUniversalServerAdmins. Si noti che ExUmContacts e PersistantChatEndPoints non sono disponibili Skype for Business Server 2019. Se è stato Skype for Business Server 2019, i cmdlet corrispondenti nei passaggi seguenti devono essere omessi.

1. Per verificare se sono presenti contatti o applicazioni associati alla Skype for Business Server locale, eseguire i cmdlet di PowerShell Skype for Business Server seguenti.

   ```PowerShell
   Get-CsMeetingRoom
   Get-CsCommonAreaPhone
   Get-CsAnalogDevice
   Get-CsExUmContact
   Get-CsDialInConferencingAccessNumber
   Get-CsRgsWorkflow
   Get-CsTrustedApplicationEndpoint
   Get-CsTrustedApplication
   Get-CsPersistentChatEndpoint
   Get-CsAudioTestServiceApplication
   Get-CsCallParkOrbit
   ```
2. Esaminare gli elenchi di output dei cmdlet nel passaggio 1. Se quindi è possibile rimuovere oggetti, eseguire i cmdlet di PowerShell Skype for Business Server seguenti:

   ```PowerShell
   Get-CsMeetingRoom | Disable-CsMeetingRoom
   Get-CsCommonAreaPhone | Remove-CsCommonAreaPhone 
   Get-CsAnalogDevice | Remove-CsAnalogDevice
   Get-CsExUmContact | Remove-CsExUmContact
   Get-CsDialInConferencingAccessNumber | Remove-CsDialInConferencingAccessNumber
   Get-CsRgsWorkflow | Remove-CsRgsWorkflow
   Get-CsTrustedApplicationEndpoint | Remove-CsTrustedApplicationEndpoint
   Get-CsTrustedApplication | Remove-CsTrustedApplication -Force
   Get-CsPersistentChatEndpoint |  Remove-CsPersistentChatEndpoint
   Get-CsCallParkOrbit | Remove-CsCallParkOrbit -Force
   Get-CsVoiceRoute | Remove-CsVoiceRoute -Force
   ```
## <a name="remove-your-on-premises-skype-for-business-deployment"></a>Rimuovere la distribuzione locale di Skype for Business

Dopo aver completato tutti i passaggi preliminari, è possibile rimuovere la Skype for Business distribuzione seguendo questi passaggi:

1. Rimuovere logicamente la Skype for Business Server distribuzione, ad eccezione di un singolo front-end, come indicato di seguito:

   1. Aggiornare la Skype for Business Server della topologia in modo che abbia un singolo pool front-end:

      1. In Generatore di topologie scaricare una nuova copia e passare al pool Frontend.
      1. Fare clic con il pulsante destro del mouse sul pool e quindi scegliere  **Modifica proprietà**.
      1. In **Associazioni** deselezionare Associa pool di server perimetrali (per i componenti multimediali) e fare clic su **OK.** 
      1. Se sono presenti più pool front-end, rimuovere associazioni per tutti i pool rimanenti.
      1. Selezionare **Azione > Rimuovi distribuzione**.
      1. Selezionare **Azione > Pubblica topologia**.

    1. Dopo aver pubblicato la topologia, completare i passaggi aggiuntivi descritti nella procedura guidata.

2. Rimuovere Skype for Business Server directory conferenze eseguendo il cmdlet di PowerShell Skype for Business Server seguente:

   ```PowerShell
   Get-CsConferenceDirectory | Remove-CsConferenceDirectory -Force
   ```

3. Completare la disinstallazione della Skype for Business Server di distribuzione eseguendo il cmdlet di PowerShell Skype for Business Server seguente:

   ```PowerShell
   Publish-CsTopology -FinalizeUninstall
   ```
   > [!NOTE]
   > Se questo passaggio restituisce un errore, aprire un ticket di supporto Microsoft per ottenere assistenza per la rimozione degli oggetti non obsoleti rimanenti.

4. Rimuovere il punto di controllo del servizio archivio di gestione centrale eseguendo il cmdlet powershell Skype for Business Server seguente:

   ```PowerShell
   Remove-CsConfigurationStoreLocation
   ``` 

5. Annullare Skype for Business Server modifiche a livello di dominio di Active Directory eseguendo il cmdlet Skype for Business Server PowerShell seguente:

   ```PowerShell
   Disable-CsAdDomain
   ```
6. Annullare Skype for Business Server modifiche a livello di foresta di Active Directory eseguendo il cmdlet Skype for Business Server PowerShell seguente:

   ```PowerShell
   Disable-CsAdForest
   ```

## <a name="see-also"></a>Vedere anche

- [Rimuovi le autorizzazioni dell'ambiente locale Skype for Business](decommission-on-prem-overview.md)

- [Spostare tutti gli utenti necessari da locale a online](decommission-move-on-prem-users.md)

- [Disabilitare la configurazione ibrida](cloud-consolidation-disabling-hybrid.md)

- [Spostare gli endpoint dell'applicazione ibrida da locale a online](decommission-move-on-prem-endpoints.md)

