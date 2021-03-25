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
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
description: Informazioni su come preparare l'infrastruttura per la distribuzione di Microsoft Teams Rooms in modo da sfruttare tutte le funzionalità.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 81aa41895f11b65c9406bd30311f2fcb974949a7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117424"
---
# <a name="prepare-your-environment"></a>Predisporre l'ambiente

Questa sezione contiene una panoramica dei passaggi necessari per preparare l'ambiente in modo da poter usare tutte le funzionalità di Microsoft Teams Rooms.
  
1. Preparare un account del dispositivo per ogni console di Microsoft Teams Rooms. Per [informazioni dettagliate, vedere Distribuire le chat room di Microsoft Teams.](rooms-deploy.md)
    
2. Verificare che sia disponibile una connessione di rete/Internet funzionante per il dispositivo da usare. 
    
   Deve essere in grado di ricevere un indirizzo IP usando il protocollo DHCP. Le chat room di Microsoft Teams non possono essere configurate con un indirizzo IP statico all'avvio della prima unità, ma successivamente è possibile configurare un indirizzo IP statico per il dispositivo nel dispositivo o nello switch o nel router upstream.

   Deve avere queste porte aperte (oltre ad aprire le porte normali per i supporti):
   - HTTPS: 443
   - HTTP: 80

   Se la rete viene eseguita tramite un proxy, sono necessarie anche le informazioni sull'indirizzo proxy o sullo script.
    
   > [!IMPORTANT]
   > Microsoft Teams Rooms non supporta l'autenticazione proxy perché può interferire con le normali operazioni della chat room. Assicurarsi che le chat room di Microsoft Teams siano state esentate dall'autenticazione proxy prima di entrare in produzione.
  
3. Per migliorare l'esperienza utente, Microsoft raccoglie i dati. Per consentire a Microsoft di raccogliere dati, consentire questi siti:

   - Endpoint client di telemetria: https://vortex.data.microsoft.com/
   - Endpoint delle impostazioni di telemetria: https://settings.data.microsoft.com/
    
### <a name="create-and-test-a-device-account"></a>Creare e testare un account del dispositivo

Un  *account del dispositivo*  è un account che il client Microsoft Teams Rooms usa per accedere alle funzionalità di Exchange, ad esempio il calendario, e per abilitare Skype for Business. Per [informazioni dettagliate, vedere Distribuire le chat room di Microsoft Teams.](rooms-deploy.md)
  
### <a name="check-network-availability"></a>Verificare la disponibilità della rete

Per funzionare correttamente, il dispositivo Microsoft Teams Rooms deve avere accesso a una rete cablata che soddisfi questi requisiti:
  
- Accesso all'istanza di Active Directory o Azure Active Directory (Azure AD), nonché ai server Microsoft Exchange e Skype for Business.

- Accesso a un server in grado di fornire un indirizzo IP tramite DHCP. Microsoft Teams Rooms non può essere configurato con un indirizzo IP statico all'avvio della prima unità.

- Accesso alle porte HTTP 80 e 443.

- Porte TCP e UDP configurate come descritto [in](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols) Requisiti di porta e protocollo per i server per le implementazioni locali di Skype for Business Server oppure URL e intervalli di indirizzi IP di Microsoft Teams e [Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) per le implementazioni online di Microsoft Teams o Skype for Business.

> [!IMPORTANT]
> Assicurarsi di usare una connessione di rete cablata da 1 Gbps per assicurarsi di avere la larghezza di banda necessaria.

> [!NOTE]
> Gli aggiornamenti software per Microsoft Teams Rooms vengono scaricati automaticamente da Microsoft Store per le aziende. Vedere [Prerequisiti per Microsoft Store per le aziende](/microsoft-store/prerequisites-microsoft-store-for-business) e l'istruzione per verificare che la console della sala sia in grado di accedere al negozio e di eseguire l'aggiornamento automatico.
  
### <a name="certificates"></a>Certificati

Il dispositivo Microsoft Teams Rooms usa certificati per i servizi Web Exchange, Microsoft Teams o Skype for Business, l'uso della rete e l'autenticazione. Se i server correlati usano certificati pubblici, come nel caso di Online e di alcune distribuzioni locali, non dovrebbero essere necessarie altre azioni da parte dell'amministratore per installare i certificati. Se, d'altra parte, l'autorità di certificazione è una CA privata (tipica per le distribuzioni locali), il dispositivo deve considerare attendibile tale CA, ovvero avere i certificati della catena CA +CA installati nel dispositivo. L'aggiunta del dispositivo al dominio può eseguire questa attività automaticamente.
  
I certificati verranno installati come per qualsiasi altro client Windows. 
  
> [!NOTE]
> Potrebbero essere necessari certificati per fare in modo che Microsoft Teams Rooms usi Skype for Business Server.
  
### <a name="proxy"></a>Proxy

Microsoft Teams Rooms è progettato per ereditare le impostazioni del proxy dal sistema operativo Windows. Accedere al sistema operativo Windows nel modo seguente:
  
1. Nell'interfaccia utente di Microsoft Teams Rooms fare clic sull'icona a forma di ingranaggio Impostazioni in cui verrà richiesta la password di amministratore locale nel dispositivo (la password predefinita è **sfb).**
2. Toccare  Impostazioni, quindi toccare il pulsante Vai a  **Windows** e quindi toccare il  pulsante Accedi amministratore e quindi fare clic sul pulsante Amministratore (se il computer fa parte del dominio scegliere **Altro utente,** quindi usare .\admin come nome utente).
3. Nella casella **Cerca in Windows** digitare in basso a sinistra in regedit (premere a lungo lo schermo o fare clic con il pulsante destro del mouse e scegliere Esegui come **amministratore).**
4. Fare clic sulla cartella HKEY_USERS (verrà visualizzato un elenco di SID degli utenti del computer) verificare che la cartella radice HKEY_USERS selezionata.
       
5. Fare clic su File e quindi **scegliere Carica hive.**
6. Passare alla **cartella C:\Utenti\Skype** e digitare nella casella Nome file NTUSER.dat e premere il pulsante Apri

7. Verrà richiesto di specificare un nome di chiave per l'hive appena caricato. digita in Skype (ora dovresti vedere le impostazioni del Registro di sistema per l'utente Skype).
 
8. Apri il tasto Skype e seleziona HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings quindi assicurati che queste impostazioni siano immesse: 
    
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
    
9. Dopo aver apportato le modifiche, evidenziare il codice Utente Skype (cartella radice per Skype) e scegliere scarica Hive dal menu File del Registro di sistema (verrà chiesto di confermare - selezionare **Sì).**
    
10. È ora possibile chiudere l'editor del Registro di sistema e digitare la disconnessione nella casella di ricerca di Windows.
    
11. Torna alla schermata di accesso, scegli **l'utente Skype.** Se tutti i passaggi precedenti hanno avuto esito positivo, il dispositivo Microsoft Teams Rooms accederà correttamente.
    
Vedere [l'articolo Sicurezza](./security.md#network-security) di rete per informazioni dettagliate su FQDN, porte e intervalli di indirizzi IP necessari per le chat room di Microsoft Teams.
  
  
### <a name="create-provisioning-packages"></a>Creare pacchetti di provisioning

I pacchetti di provisioning verranno utilizzati per l'autenticazione Exchange Server, Microsoft 365 o Office 365.
  
### <a name="admin-group-management"></a>Gestione dei gruppi di amministratori

Dopo l'aggiunta al dominio, è possibile usare Criteri di gruppo o Gestione computer locale per impostare un gruppo di sicurezza come amministratore locale come per un PC Windows nel dominio. Chiunque sia membro di quel gruppo di sicurezza può immettere le proprie credenziali e sbloccare Le impostazioni.
  
> [!NOTE]
> Se il dispositivo Microsoft Teams Rooms perde la relazione di trust con il dominio, ad esempio se si rimuovono le chat room di Microsoft Teams dal dominio dopo che è stato aggiunto al dominio, non sarà possibile eseguire l'autenticazione nel dispositivo e aprire Impostazioni. La soluzione alternativa consiste nell'accedere con l'account di amministratore locale. 
  
## <a name="local-accounts"></a>Account locali

### <a name="microsoft-teams-rooms-local-user-account"></a>Account utente locale di Microsoft Teams Rooms

L'account del dispositivo in genere non usa una password. È possibile assegnare una password, ma ci sono conseguenze, tra cui la possibilità che gli utenti siano bloccati dall'applicazione console alla scadenza della password. Di conseguenza, l'amministratore deve assicurarsi che la password non scada.
  
### <a name="admin---local-administrator-account"></a>"Amministratore" - Account di amministratore locale

La password predefinita di Microsoft Teams Rooms è impostata su "sfb". La password può essere cambiata localmente in Impostazioni di Windows Passare a Windows o nel file AutoUnattend.xml (usare Windows System Image Manager da ADK per apportare la modifica al \> file XML).
  
> [!CAUTION]
> Assicurarsi di cambiare la password di Microsoft Teams Rooms il prima possibile. 
  
È anche possibile gestire la password dell'amministratore locale configurando un criterio di gruppo in cui gli amministratori di dominio sono amministratori locali.
  
La password di amministratore locale non è inclusa come scelta durante l'installazione.
  
### <a name="machine-account"></a>Account computer

Come qualsiasi dispositivo Windows, il nome del computer può essere rinominato facendo clic con il pulsante destro del mouse in **Impostazioni** \> **su** \> **Rinomina PC.**
  
Se si vuole rinominare il computer dopo l'aggiunta a un dominio, usare **Rename-Computer**, un comando di PowerShell seguito dal nuovo nome del computer.
  
## <a name="related-topics"></a>Argomenti correlati

[Pianificare le sale di Microsoft Teams](rooms-plan.md)

[Requisiti per Microsoft Teams Rooms](requirements.md)
  
[Distribuire Microsoft Teams Rooms](rooms-deploy.md)
  
[Configurare una console per Microsoft Teams Rooms](console.md)
  
[Gestire Microsoft Teams Rooms](rooms-manage.md).

[Prerequisiti per Microsoft Store per le aziende e l'istruzione](/microsoft-store/prerequisites-microsoft-store-for-business)