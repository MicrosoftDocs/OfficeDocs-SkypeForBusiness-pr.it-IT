---
title: Rimuovere le autorizzazioni di Skype for Business Server
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
description: Istruzioni per la rimozione di Skype for Business Server.
ms.openlocfilehash: 668e3d5ebf5dfa03fcfb883adcc3e08fc5924bae
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593908"
---
# <a name="remove-your-on-premises-skype-for-business-deployment"></a>Rimuovere la distribuzione locale di Skype for Business

Questo articolo descrive come rimuovere la distribuzione locale di Skype for Business. Questo è il passaggio 3 della procedura seguente per rimuovere le autorizzazioni dell'ambiente locale:

- Passaggio 1. [Spostare tutti gli utenti e gli endpoint dell'applicazione necessari da](decommission-move-on-prem-users.md)locale a online. 

- Passaggio 2. [Disabilitare la configurazione ibrida](cloud-consolidation-disabling-hybrid.md).

- **Passaggio 3. Rimuovere la distribuzione locale di Skype for Business.** (Questo articolo)


> [!IMPORTANT] 
> La procedura descritta in questo articolo si applica solo se si utilizza il metodo 2 per la gestione degli attributi utente, come descritto [qui.](cloud-consolidation-disabling-hybrid.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory) Se si utilizza il metodo 1, non eseguire la procedura descritta in questo articolo per rimuovere i server Skype for Business. Al contrario, è possibile ri-immagine dei server.

Per completare i passaggi descritti in questo articolo, sono necessari privilegi sia per il gruppo Schema Admins che per il gruppo Enterprise Admin. Questi privilegi sono necessari per annullare lo schema di Skype for Business Server e le modifiche a livello di foresta in Servizi di dominio Active Directory. Sarà inoltre necessario essere membri del gruppo RTCUniversalServerAdmins.


## <a name="prepare-to-remove-the-skype-for-business-deployment"></a>Preparare la rimozione della distribuzione di Skype for Business

Dopo aver spostato tutti gli account utente necessari nel cloud, potrebbero essere ancora presenti alcuni oggetti locali rimanenti, ad esempio contatti e applicazioni, che sarà necessario pulire.

Eseguire la procedura seguente per pulire questi oggetti e assicurarsi di essere membri sia del gruppo Amministratore locale che del gruppo RTCUniversalServerAdmins. Si noti che ExUmContacts e PersistantChatEndPoints non sono disponibili in Skype for Business Server 2019. Se si dispone di Skype for Business Server 2019, i cmdlet corrispondenti nei passaggi seguenti devono essere omessi.

1. Per verificare se sono presenti contatti o applicazioni associati alla distribuzione locale di Skype for Business Server, eseguire i cmdlet di PowerShell di Skype for Business Server seguenti.

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
2. Esaminare gli elenchi di output dei cmdlet nel passaggio 1. Quindi, se gli oggetti possono essere rimossi, eseguire i cmdlet di PowerShell di Skype for Business Server seguenti:

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

Dopo aver completato tutti i passaggi preliminari, è possibile rimuovere la distribuzione di Skype for Business seguendo questi passaggi:

1. Rimuovere logicamente la distribuzione di Skype for Business Server, ad eccezione di un singolo front-end, come indicato di seguito:

   a. Aggiornare la topologia di Skype for Business Server in modo che abbia un singolo pool front-end:

     - In Generatore di topologie scaricare una nuova copia e passare al pool Frontend.
     - Fare clic con il pulsante destro del mouse sul pool e quindi scegliere  **Modifica proprietà**.
     - In **Associazioni** deselezionare Associa pool di server perimetrali (per i componenti multimediali) e fare clic su **OK.** 
     - Se sono presenti più pool front-end, rimuovere associazioni per tutti i pool rimanenti.
     - Selezionare **Azione > Rimuovi distribuzione**.
     - Selezionare **Azione > Pubblica topologia**.

    b. Dopo aver pubblicato la topologia, completare i passaggi aggiuntivi descritti nella procedura guidata.

2. Rimuovere le directory conferenze di Skype for Business Server eseguendo il cmdlet di PowerShell di Skype for Business Server seguente:

   ```PowerShell
   Get-CsConferenceDirectory | Remove-CsConferenceDirectory -Force
   ```

3. Completare la disinstallazione della distribuzione di Skype for Business Server eseguendo il cmdlet di PowerShell di Skype for Business Server seguente:

   ```PowerShell
   Publish-CsTopology -FinalizeUninstall
   ```
   > [!NOTE]
   > Se questo passaggio restituisce un errore, aprire un ticket di supporto Microsoft per ottenere assistenza per la rimozione degli oggetti non obsoleti rimanenti.

4. Rimuovere il punto di controllo del servizio Archivio di gestione centrale eseguendo il cmdlet di PowerShell di Skype for Business Server seguente:

   ```PowerShell
   Remove-CsConfigurationStoreLocation
   ``` 

5. Annullare le modifiche a livello di foresta del dominio Active Directory di Skype for Business Server eseguendo il cmdlet di PowerShell di Skype for Business Server seguente:

   ```PowerShell
   Disable-CsAdDomain
   ```
6. Annullare le modifiche allo schema del dominio di Active Directory di Skype for Business Server eseguendo il cmdlet di PowerShell di Skype for Business Server seguente:

   ```PowerShell
   Disable-CsAdForest
   ```

## <a name="see-also"></a>Vedere anche

- [Rimuovere le autorizzazioni dell'ambiente Skype for Business locale](decommission-on-prem-overview.md)

- [Spostare utenti ed endpoint nel cloud](decommission-move-on-prem-users.md)

- [Disabilitare la configurazione ibrida](cloud-consolidation-disabling-hybrid.md)














