---
title: Preparare l'ambiente
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
description: Informazioni su come preparare l'infrastruttura per la distribuzione di Microsoft Teams Rooms in modo da poter sfruttare tutte le caratteristiche.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7006f560c5d0991b74c14fc5eb0b13e829b642d9
ms.sourcegitcommit: 8dd36e1e30a47316c15c99e964d0464715bcd742
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2022
ms.locfileid: "68532226"
---
# <a name="prepare-your-environment"></a>Predisporre l'ambiente

Questa sezione contiene una panoramica dei passaggi necessari per preparare l'ambiente in modo da poter usare tutte le caratteristiche di Microsoft Teams Rooms.
  
1. Preparare un account di risorse per ogni console Microsoft Teams Rooms. Per informazioni dettagliate[, vedere Distribuire Microsoft Teams Rooms](rooms-deploy.md).
    
2. Assicurati che sia disponibile una connessione di rete/Internet funzionante per il dispositivo da usare.
  
3. Per migliorare la tua esperienza, Microsoft raccoglie i dati. Per consentire a Microsoft di raccogliere dati, consenti questi siti:

   - Endpoint client di telemetria: `https://vortex.data.microsoft.com/`
   - Endpoint delle impostazioni di telemetria:` https://settings.data.microsoft.com/`
    
### <a name="create-and-test-a-resource-account"></a>Creare e testare un account di risorsa

Un *account delle risorse* è un account usato dal client Microsoft Teams Rooms per accedere alle funzionalità di Exchange, come il calendario, e per connettersi a Microsoft Teams. Per informazioni dettagliate[, vedere Distribuire Microsoft Teams Rooms](rooms-deploy.md).
  
### <a name="check-network-availability"></a>Verificare la disponibilità della rete

Per funzionare correttamente, Microsoft Teams Rooms deve avere accesso a una rete cablata che soddisfa questi requisiti:
  
- Accesso all'istanza di Active Directory o Azure Active Directory (Azure AD), nonché a Microsoft Exchange e Microsoft Teams.

- Accesso a un server in grado di fornire un indirizzo IP tramite DHCP. Microsoft Teams Rooms non può essere configurato con un indirizzo IP statico all'avvio della prima unità.

- Accesso alle porte HTTP 80 e 443.

- Porte TCP e UDP configurate come descritto in Requisiti di porte [e protocollo per i server](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols) per implementazioni di Skype for Business Server locali o [URL e intervalli di indirizzi IP di Microsoft 365 e Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) per Microsoft Teams.

Se la rete viene eseguita tramite un proxy, sono necessarie anche le informazioni relative all'indirizzo proxy o allo script.
    
> [!IMPORTANT]
> Microsoft Teams Rooms non supporta l'autenticazione proxy in quanto potrebbe interferire con le normali operazioni della chat room. Assicurarsi che Microsoft Teams Rooms siano state esenti dall'autenticazione proxy prima di entrare in produzione.

> [!IMPORTANT]
> Assicurati di utilizzare una connessione di rete cablata 1 Gbps per assicurarti di avere la larghezza di banda necessaria.

> [!NOTE]
> Gli aggiornamenti software per Microsoft Teams Rooms vengono scaricati automaticamente dal Microsoft Store per le aziende. Vedi [Prerequisiti per Microsoft Store per le aziende ed Istruzione](/microsoft-store/prerequisites-microsoft-store-for-business) per verificare che la console della sala possa accedere allo Store e all'aggiornamento automatico.
  
### <a name="certificates"></a>Certificati

Il dispositivo Microsoft Teams Rooms utilizza certificati per Servizi Web Exchange, Microsoft Teams o Skype for Business, utilizzo della rete e autenticazione. Se i server correlati usano certificati pubblici, nel caso di distribuzioni online e locali, non dovrebbero essere necessarie altre azioni da parte dell'amministratore per installare i certificati. Se, invece, l'autorità di certificazione è una CA privata, il dispositivo deve considerare attendibile tale CA. Ciò significa che nel dispositivo sono installati i certificati della catena CA + CA. L'aggiunta del dispositivo al dominio può eseguire questa attività automaticamente.
  
I certificati verranno installati come per qualsiasi altro client Windows.

> [!IMPORTANT]
> Se il server proxy utilizza certificati firmati internamente, è necessario installare la catena di certificati interna, inclusa la CA radice, nel dispositivo Microsoft Teams Rooms.
  
> [!NOTE]
> Per usare Microsoft Teams Rooms Skype for Business Server, possono essere necessari certificati.
  
### <a name="proxy"></a>Proxy

Microsoft Teams Rooms è progettato per ereditare le impostazioni proxy dal sistema operativo Windows. Accedere al sistema operativo Windows nel modo seguente:
  
1. Nell'interfaccia utente Microsoft Teams Rooms fai clic sull'icona a forma di ingranaggio Impostazioni in cui ti verrà richiesto di specificare la password dell'amministratore locale nel dispositivo (la password predefinita è **sfb**).
2. Tocca **Impostazioni**, quindi tocca il pulsante **Vai a Windows** e quindi tocca il pulsante **Vai a Amministrazione Accedi** e quindi fai clic sul pulsante **Amministratore** (se il computer fa parte di un dominio **, scegli Altro utente,** usa .\admin come nome utente).
3. Nella casella **Cerca in basso** a sinistra digitare regedit (premere a lungo lo schermo o fare clic con il pulsante destro del mouse e scegliere **Esegui come amministratore**).
4. Fare clic sulla cartella HKEY_USERS (verrà visualizzato un elenco di SID utente computer) assicurarsi che la cartella radice HKEY_USERS sia selezionata.
       
5. Fare clic su File e quindi scegliere **Carica Hive.**
6. Passare alla cartella **C:\Users\Skype** e digitare nella casella Nome file NTUSER.dat e premere il pulsante Apri

7. Ti verrà richiesto un nome di chiave per il nuovo hive caricato; digita in Skype (ora dovresti vedere le impostazioni del Registro di sistema per l'utente Skype).
 
8. Apri il tasto Skype e passa a HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings quindi verifica che siano state immesse queste impostazioni: 
    
    ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "ProxyServer"="xx.xx.xx.xx:8080"
    ```
    
    Se ProxyServer non esiste, potrebbe essere necessario aggiungere questa chiave come stringa, sostituire xx.xx.xx.xx:8080 con ip/host e porta del server Proxy.
 
    Se il cliente usa un file PAC, la configurazione sarà simile all'esempio seguente:

     ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "AutoConfigURL"=http://contosoproxy.corp.net/proxy.pac
    ```
    
9. Dopo aver apportato le modifiche, evidenzia la chiave utente Skype (cartella radice per Skype) e scegli scarica Hive dal menu file del Registro di sistema (ti verrà richiesta la conferma- seleziona **Sì**).
    
10. Ora puoi chiudere l'editor del Registro di sistema e digitare logoff nella casella di ricerca di Windows.
    
11. Torna alla schermata di accesso, scegli l'utente **Skype** . Se tutti i passaggi precedenti hanno avuto esito positivo, il dispositivo Microsoft Teams Rooms eseguirà correttamente l'accesso.
    
Per informazioni dettagliate su FQDN, porte e intervalli di indirizzi IP necessari per Microsoft Teams Rooms, vedere l'articolo [Sicurezza](./security-windows.md#network-security) della rete.
  
### <a name="admin-group-management"></a>gestione dei gruppi di Amministrazione

Se si sceglie di aggiungersi a un dominio (Azure Active Directory o Active Directory), è possibile usare Microsoft Endpoint Manager, Criteri di gruppo o Gestione computer locale per impostare un gruppo di sicurezza come amministratore locale come per un PC Windows nel dominio. Chiunque sia membro di tale gruppo di sicurezza può immettere le proprie credenziali e sbloccare le impostazioni.
  
> [!NOTE]
> Se il dispositivo Microsoft Teams Rooms perde l'attendibilità con il dominio (ad esempio, se si rimuove il Microsoft Teams Rooms dal dominio dopo l'aggiunta al dominio), non sarà possibile eseguire l'autenticazione nel dispositivo e aprire Le impostazioni. La soluzione alternativa consiste nell'accedere con l'account amministratore locale. 
  
## <a name="local-accounts"></a>Account locali

### <a name="microsoft-teams-rooms-local-user-account"></a>account utente locale Microsoft Teams Rooms

Teams Rooms include un account locale senza password denominato "Skype". Questo account viene usato per accedere a Windows per avviare l'app Teams Rooms. Non è supportato l'applicazione di una password a questo account. Per altre informazioni, vedere [Microsoft Teams Rooms Security](security-windows.md).
  
### <a name="admin---local-administrator-account"></a>"Amministrazione" - Account amministratore locale

Microsoft Teams Rooms password predefinita è impostata su "sfb". La password può essere modificata localmente tramite la modalità Amministrazione o nel file di AutoUnattend.xml (utilizzare Gestione immagini di sistema di Windows da ADK per apportare la modifica al file xml).
  
> [!CAUTION]
> Assicurati di cambiare la password Microsoft Teams Rooms il prima possibile. 
  
La password dell'amministratore locale non è inclusa come scelta durante l'installazione.

Per altre informazioni sull'account di Amministrazione, vedere l'articolo [sulla sicurezza di Microsoft Teams Rooms](security-windows.md).
  
### <a name="machine-account"></a>Account computer

Analogamente a qualsiasi dispositivo Windows, il nome del computer può essere rinominato facendo clic con il pulsante destro del mouse in **Impostazioni** \> **su** \> **Rinomina PC**.
  
Per rinominare il computer dopo averlo unito a un dominio, usare [Rinomina-Computer](/powershell/module/microsoft.powershell.management/rename-computer), un comando di PowerShell seguito dal nuovo nome del computer.
  
## <a name="related-topics"></a>Argomenti correlati

[Pianificare Microsoft Teams Rooms](rooms-plan.md)

[Requisiti per Microsoft Teams Rooms](requirements.md)
  
[Distribuire Microsoft Teams Rooms](rooms-deploy.md)
  
[Configurare una console per Microsoft Teams Rooms](console.md)
  
[Gestire Microsoft Teams Rooms](rooms-manage.md).

[Prerequisiti per Microsoft Store per le aziende e l'istruzione](/microsoft-store/prerequisites-microsoft-store-for-business)
