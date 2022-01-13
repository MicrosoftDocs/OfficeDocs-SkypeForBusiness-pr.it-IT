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
description: Informazioni su come preparare l'infrastruttura per la distribuzione di Microsoft Teams Rooms in modo da poter sfruttare tutte le funzionalità.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b92325fe9c7c43497fd9647306cfb6b218f5fde0
ms.sourcegitcommit: d2c76fe7705acf6e53f7673861671b1b018813dd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2022
ms.locfileid: "62015036"
---
# <a name="prepare-your-environment"></a>Predisporre l'ambiente

Questa sezione contiene una panoramica dei passaggi necessari per preparare l'ambiente in modo da poter usare tutte le funzionalità di Microsoft Teams Rooms.
  
1. Preparare un account delle risorse per ogni Microsoft Teams Rooms console. Per [informazioni dettagliate, vedere Microsoft Teams Rooms](rooms-deploy.md) distribuzione.
    
2. Verificare che sia disponibile una connessione di rete/Internet funzionante per il dispositivo da usare.
  
3. Per migliorare l'esperienza utente, Microsoft raccoglie i dati. Per consentire a Microsoft di raccogliere dati, consentire questi siti:

   - Endpoint client di telemetria: https://vortex.data.microsoft.com/
   - Endpoint delle impostazioni di telemetria: https://settings.data.microsoft.com/
    
### <a name="create-and-test-a-resource-account"></a>Creare e testare un account della risorsa

Un *account delle risorse* è un account che il client Microsoft Teams Rooms usa per accedere alle funzionalità da Exchange, ad esempio il calendario, e per connettersi a Microsoft Teams. Per [informazioni dettagliate, vedere Microsoft Teams Rooms](rooms-deploy.md) distribuzione.
  
### <a name="check-network-availability"></a>Verificare la disponibilità della rete

Per funzionare correttamente, Microsoft Teams Rooms deve avere accesso a una rete cablata che soddisfi questi requisiti:
  
- Accesso all'istanza di Active Directory o Azure Active Directory (Azure AD), nonché a Microsoft Exchange e Microsoft Teams.

- Accesso a un server in grado di fornire un indirizzo IP tramite DHCP. Microsoft Teams Rooms non può essere configurato con un indirizzo IP statico al primo avvio dell'unità.

- Accesso alle porte HTTP 80 e 443.

- Le porte TCP e UDP configurate come descritto [in](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols) Requisiti di porta e protocollo per i server per le implementazioni di Skype for Business Server locali o URL di Microsoft 365 e Office 365 e intervalli di indirizzi [IP](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) per Microsoft Teams.

Se la rete viene eseguita tramite un proxy, sono necessarie anche le informazioni sull'indirizzo proxy o sullo script.
    
> [!IMPORTANT]
> Microsoft Teams Rooms non supporta l'autenticazione proxy perché può interferire con le normali operazioni della chat room. Assicurarsi che Microsoft Teams Rooms siano stati esenti dall'autenticazione proxy prima di entrare in produzione.

> [!IMPORTANT]
> Assicurarsi di usare una connessione di rete cablata da 1 Gbps per assicurarsi di avere la larghezza di banda necessaria.

> [!NOTE]
> Gli aggiornamenti software per Microsoft Teams Rooms vengono scaricati automaticamente dal Microsoft Store per le aziende. Vedere [Prerequisiti per Microsoft Store per le aziende e Education](/microsoft-store/prerequisites-microsoft-store-for-business) per verificare che la console della sala sia in grado di accedere al negozio e di eseguire l'aggiornamento automatico.
  
### <a name="certificates"></a>Certificati

Il dispositivo Microsoft Teams Rooms usa certificati per Exchange web services, Microsoft Teams o Skype for Business, l'utilizzo della rete e l'autenticazione. Se i server correlati usano certificati pubblici, come nel caso di distribuzioni online e locali, non dovrebbero essere necessarie altre azioni da parte dell'amministratore per installare i certificati. Se invece l'autorità di certificazione è una CA privata, il dispositivo deve considerare attendibile tale CA. Questo significa che nel dispositivo sono installati i certificati della catena CA +CA. L'aggiunta del dispositivo al dominio può eseguire questa attività automaticamente.
  
I certificati verranno installati come per qualsiasi altro client Windows client. 
  
> [!NOTE]
> I certificati possono essere necessari per Microsoft Teams Rooms usare Skype for Business Server.
  
### <a name="proxy"></a>Proxy

Microsoft Teams Rooms è progettato per ereditare le impostazioni proxy dal Windows sistema operativo. Accedere al Windows sistema operativo nel modo seguente:
  
1. Nell'interfaccia Microsoft Teams Rooms, fare clic sull'icona Impostazioni a forma di ingranaggio in cui verrà richiesta la password di amministratore locale nel dispositivo (la password predefinita è **sfb).**
2. Toccare **Impostazioni** seguito dal pulsante Vai **a Windows** e quindi toccare il  pulsante Accedi amministratore e quindi  fare clic sul pulsante Amministratore (se il computer fa parte del dominio scegliere **Altro utente,** quindi usare .\admin come nome utente).
3. Nella casella **Cerca Windows** in basso a sinistra in regedit (premere a lungo lo schermo o fare clic con il pulsante destro del mouse e scegliere Esegui **come amministratore).**
4. Fare clic sulla cartella HKEY_USERS (verrà visualizzato un elenco di SID degli utenti del computer) verificare che la cartella radice HKEY_USERS selezionata.
       
5. Fare clic su File e quindi **scegliere Carica hive.**
6. Passare alla **cartella C:\Users\Skype** e digitare nella casella Nome file NTUSER.dat e premere il pulsante Apri

7. Verrà richiesto di specificare un nome di chiave per l'hive appena caricato. digitare Skype (ora dovrebbero essere presenti le impostazioni del Registro di sistema per l'Skype utente).
 
8. Aprire il Skype chiave e passare a HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings quindi verificare che le impostazioni siano immesse: 
    
    ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "ProxyServer"="xx.xx.xx.xx:8080"
    ```
    
    Se ProxyServer non esiste, potrebbe essere necessario aggiungere questa chiave come stringa, modificare xx.xx.xx.xx:8080 nell'ip/host e nella porta del server proxy.
 
    Se il cliente usa un file PAC, la configurazione sarà simile all'esempio seguente:

     ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "AutoConfigURL"=http://contosoproxy.corp.net/proxy.pac
    ```
    
9. Dopo aver apportato le modifiche, evidenziare la chiave utente Skype (cartella radice per Skype) e scegliere scarica Hive dal menu File del Registro di sistema (verrà chiesto di confermare - selezionare **Sì**).
    
10. È ora possibile chiudere l'editor del Registro di sistema e digitare la disconnessione nella Windows di ricerca.
    
11. Tornare alla schermata di accesso, scegliere l'Skype **utente.** Se tutti i passaggi precedenti hanno avuto esito positivo, Microsoft Teams Rooms il dispositivo di accesso verrà eseguito correttamente.
    
Vedere [l'articolo Sicurezza](./security.md#network-security) di rete per informazioni dettagliate su FQDN, porte e intervalli di indirizzi IP necessari per Microsoft Teams Rooms.
  
### <a name="admin-group-management"></a>Gestione dei gruppi di amministratori

Se si sceglie di partecipare a un dominio (Azure Active Directory o Active Directory), è possibile usare Microsoft Endpoint Manager, Criteri di gruppo o Gestione computer locale per impostare un gruppo di sicurezza come amministratore locale come per un PC Windows nel dominio. Chiunque sia membro di quel gruppo di sicurezza può immettere le proprie credenziali e sbloccare Impostazioni.
  
> [!NOTE]
> Se il dispositivo Microsoft Teams Rooms perde la relazione di trust con il dominio, ad esempio se si rimuove il Microsoft Teams Rooms dal dominio dopo che è stato aggiunto al dominio, non sarà possibile eseguire l'autenticazione nel dispositivo e aprire Impostazioni. La soluzione alternativa consiste nell'accedere con l'account amministratore locale. 
  
## <a name="local-accounts"></a>Account locali

### <a name="microsoft-teams-rooms-local-user-account"></a>Microsoft Teams Rooms account utente locale

Teams Rooms include un account locale senza password denominato "Skype". Questo account viene usato per accedere a Windows per avviare l Teams Rooms app. Non è supportato l'applicazione di una password a questo account. Per [altre informazioni, Microsoft Teams Rooms sicurezza.](security.md)
  
### <a name="admin---local-administrator-account"></a>"Amministratore" - Account di amministratore locale

Microsoft Teams Rooms password predefinita è impostata su "sfb". La password può essere modificata localmente tramite la modalità di amministrazione o nel file AutoUnattend.xml (usare Windows System Image Manager da ADK per apportare la modifica al file XML).
  
> [!CAUTION]
> Assicurarsi di cambiare la password Microsoft Teams Rooms non appena possibile. 
  
La password di amministratore locale non è inclusa come scelta durante l'installazione.

Per altre informazioni sull'account amministratore, vedere [l'articolo Microsoft Teams Rooms Sicurezza.](security.md)
  
### <a name="machine-account"></a>Account computer

Come qualsiasi dispositivo Windows, il nome del computer può essere rinominato facendo clic con il pulsante destro del mouse **Impostazioni** \> **su** \> **Rinomina PC.**
  
Se si vuole rinominare il computer dopo l'aggiunta a un dominio, usare [Rename-Computer](/powershell/module/microsoft.powershell.management/rename-computer?view=powershell-7.2), un comando di PowerShell seguito dal nuovo nome del computer.
  
## <a name="related-topics"></a>Argomenti correlati

[Pianificare Microsoft Teams Rooms](rooms-plan.md)

[Requisiti per Microsoft Teams Rooms](requirements.md)
  
[Distribuire Microsoft Teams Rooms](rooms-deploy.md)
  
[Configurare una console per Microsoft Teams Rooms](console.md)
  
[Gestire Microsoft Teams Rooms](rooms-manage.md).

[Prerequisiti per l'Microsoft Store per le aziende e l'istruzione](/microsoft-store/prerequisites-microsoft-store-for-business)
