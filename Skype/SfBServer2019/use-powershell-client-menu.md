---
title: Usare PowerShell per le attività nel menu Client
ms.reviewer: ''
ms.author: v-smandalika
author: v-smandalika
manager: dansimp
ms.date: 10/12/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: ''
description: 'Riepilogo: Skype for Business Server pannello di controllo al mapping cmdlet per il menu Client.'
ms.openlocfilehash: 1dc0c3a9638af8fdec90fccb633909b9ccf40405
ms.sourcegitcommit: eba9fc680233e9e03773a2942f22afe6247eec41
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60824654"
---
# <a name="client"></a>Client

In questo articolo viene descritto come ottenere risultati simili a quelli della voce di menu **Client** nel Pannello di controllo legacy utilizzando i cmdlet.

In questo articolo vengono descritti i sottomenu seguenti:

- [Client](#client)
  - [Criteri delle versioni client](#client-version-policy)
  - [Configurazione delle versioni client](#client-version-configuration)
  - [Aggiornamento dei dispositivi](#device-update)
  - [Dispositivo di test](#test-device)
  - [Configurazione dei log del dispositivo](#device-log-configuration)
  - [Configurazione dispositivo](#device-configuration)
  - [Criteri per dispositivi mobili](#mobility-policy)
  - [Configurazione notifica Push](#push-notification-configuration)

## <a name="client-version-policy"></a>Criteri delle versioni client

La voce di sottomenu **CLIENT VERSION POLICY** nel menu **Client** restituisce informazioni sui client supportati in Skype for Business Server ambiente. Un criterio di versione client consente di specificare i client che possono accedere a Skype for Business Server sistema.

Prendiamo in considerazione le varie attività che un utente può eseguire su **CLIENT VERSION POLICY** e i cmdlet Skype for Business a cui tali attività sono mappate.

---
> **Scenario 1:** elencare tutti i criteri delle versioni client

   ![Elenco criteri versione client](./media/clientversionpolicy-1.png)

***Cmdlet***

[Get-CsClientVersionPolicy](/powershell/module/skype/get-csclientversionpolicy)

***Esempio***

```powershell
 Get-CsClientVersionPolicy
```

---

> **Scenario 2:** creare un nuovo criterio di versione client

   ![Nuovi criteri versione client](./media/clientversionpolicy-2.png)

***Cmdlet***

[New-CsClientVersionPolicy](/powershell/module/skype/new-csclientversionpolicy)  

***Esempio***

```powershell
 New-CsClientVersionPolicy -Identity site:Redmond
```

---

> **Scenario 3:** ottenere i dettagli di un criterio di versione client scelto

   ![Ottenere i criteri versione client](./media/clientversionpolicy-3.png)

***Cmdlet***

[Get-CsClientVersionPolicy](/powershell/module/skype/get-csclientversionpolicy)

***Esempio***

```powershell
 Get-CsClientVersionPolicy -Identity site:Redmond
```

---

> **Scenario 4**: Eliminare i criteri delle versioni client selezionati

   ![Elimina criteri versione client](./media/clientversionpolicy-4.png)

***Cmdlet***

[Remove-CsClientVersionPolicy](/powershell/module/skype/remove-csclientversionpolicy)

***Esempio***

```powershell
 Remove-CsClientVersionPolicy -Identity site:Redmond
```

---

> **Scenario 5:** aggiornare un criterio di versione client

   ![Aggiornare i criteri versione client](./media/clientversionpolicy-5.png)

- **Annotazione 1 - Risultato**

    Questa annotazione sull'immagine indica un risultato, cio? i dati recuperati e visualizzati.

    ***Cmdlet***

    [Get-CsClientVersionPolicyRule](/powershell/module/skype/get-csclientversionpolicyrule)

    ***Esempio***

    ```powershell
    Get-CsClientVersionPolicyRule -Filter "Global/*"
    ```

- **Annotazione 2 - Opzione (per l'utente)**

    Questa annotazione sull'immagine indica un'opzione che l'utente può implementare, cio? per ottenere i dettagli delle regole dei criteri della versione client.

    ***Cmdlet***

    [Get-CsClientVersionPolicyRule](/powershell/module/skype/get-csclientversionpolicyrule)

    ***Esempio***

    ```powershell
    Get-CsClientVersionPolicyRule -Identity "Global/2336c611-a243-4c5d-994b-eea8a524d0e4"
    ```

- **Annotazione 3 - Opzione (per l'utente)**

    Questa annotazione sull'immagine indica un'opzione che l'utente può implementare, cio? per creare una nuova regola dei criteri della versione client.

    ***Cmdlet***

    [New-CsClientVersionPolicyRule](/powershell/module/skype/new-csclientversionpolicyrule)

    ***Esempio***

    ```powershell
    $x = \[guid\]::NewGuid()

    New-CsClientVersionPolicyRule -Parent "site:Redmond" -RuleId $x -MajorVersion 4 -UserAgent InHouse
    ```

- **Annotazione 4 - Opzione (per l'utente)**

    Questa annotazione sull'immagine indica un'opzione che l'utente può implementare, cio? per eseguire il commit/salvare la regola dei criteri della versione client appena creata.

    ***Cmdlet***

    [Set-CsClientVersionPolicy](/powershell/module/skype/set-csclientversionpolicy)

    ***Esempio***

    ```powershell
    Set-CsClientVersionPolicy -Identity site:Redmond -Rules $Null

    $x = Get-CsClientVersionPolicy -Identity site:Dublin | Select-Object -ExpandProperty Rules

    Set-CsClientVersionPolicy -Identity site:Redmond -Rules $x
    ```

---

## <a name="client-version-configuration"></a>Configurazione versione client

 La voce del sottomenu **CLIENT VERSION CONFIGURATION** restituisce informazioni sui client supportati Skype for Business Server ambiente.

Prendere in considerazione le varie attività che un utente può eseguire in **CLIENT VERSION CONFIGURATION** e i cmdlet Skype for Business a cui tali attività sono mappate.

---
> **Scenario 1:** elencare tutte le configurazioni delle versioni client

   ![List Client Version Configuration](./media/ClientVersionConfiguration-1.png)

***Cmdlet***

[Get-CsClientVersionConfiguration](/powershell/module/skype/get-csclientversionconfiguration)

***Esempio***

```powershell
 Get-CsClientVersionConfiguration
```

---

> **Scenario 2:** creare una nuova configurazione della versione client

   ![Creare la configurazione della versione client](./media/ClientVersionConfiguration-2.png)

***Cmdlet***

[New-CsClientVersionConfiguration](/powershell/module/skype/new-csclientversionconfiguration)  

***Esempio***

```powershell
 New-CsClientVersionConfiguration -Identity site:Redmond -Enabled $False
```

---

> **Scenario 3:** ottenere i dettagli di una configurazione della versione client scelta

   ![Ottenere la configurazione della versione client](./media/ClientVersionConfiguration-3.png)

***Cmdlet***

[Get-CsClientVersionConfiguration](/powershell/module/skype/get-csclientversionconfiguration)

***Esempio***

```powershell
 Get-CsClientVersionConfiguration -Identity site:Redmond
```

---

> **Scenario 4**: Eliminare le configurazioni delle versioni client selezionate

   ![Elimina configurazione versione client](./media/ClientVersionConfiguration-4.png)

***Cmdlet***

[Remove-CsClientVersionConfiguration](/powershell/module/skype/remove-csclientversionconfiguration)

***Esempio***

```powershell
 Remove-CsClientVersionConfiguration -Identity site:Redmond
```

---

> **Scenario 5:** aggiornare una configurazione della versione client

   ![Aggiornare la configurazione della versione client](./media/ClientVersionConfiguration-5.png)

***Cmdlet***

[Set-CsClientVersionConfiguration](/powershell/module/skype/set-csclientversionconfiguration)

***Esempio***

```powershell
Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration -DefaultURL "https://litwareinc.com/csclients"
```

---

> **Scenario 6:** abilitare/disabilitare le configurazioni delle versioni client

![Abilita configurazione versione client](./media/ClientVersionConfiguration-6.png)

***Cmdlet***

[Set-CsClientVersionConfiguration](/powershell/module/skype/set-csclientversionconfiguration)

***Esempio***

```powershell
Set-CsClientVersionConfiguration -Identity site:Redmond -Enabled $False
```

---

## <a name="device-update"></a>Aggiornamento dispositivi

**Le regole DEVICE UPDATE** vengono utilizzate per associare gli aggiornamenti del firmware ai dispositivi che eseguono Skype for Business Telefono Edition.

Prendiamo in considerazione le varie attività che un utente può eseguire su **DEVICE UPDATE** e i cmdlet Skype for Business a cui tali attività sono mappate.

---
> **Scenario 1:** elencare tutti gli aggiornamenti dei dispositivi

   ![Elenco aggiornamento dispositivi](./media/device-update-1.png)

***Cmdlet***

[Get-CsDeviceUpdateRule](/powershell/module/skype/get-csdeviceupdaterule)

***Esempio***

```powershell
 Get-CsDeviceUpdateRule
```

---

> **Scenario 2:** eliminare gli aggiornamenti dei dispositivi

   ![Elimina aggiornamento dispositivi](./media/device-update-2.png)

***Cmdlet***

[Remove-CsDeviceUpdateRule](/powershell/module/skype/remove-csdeviceupdaterule)  

***Esempio***

```powershell
 Remove-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9
```

---

> **Scenario 3:** annullare gli aggiornamenti dei dispositivi

   ![Annullare l'aggiornamento dei dispositivi](./media/device-update-3.png)

***Cmdlet***

[Clear-CsDeviceUpdateFile](/powershell/module/skype/clear-csdeviceupdatefile)

***Esempio***

```powershell
 Clear-CsDeviceUpdateFile -Identity "service:WebServer:atl-cs-001.litwareinc.com"
```

---

> **Scenario 4**: Approvare gli aggiornamenti dei dispositivi

   ![Approvare l'aggiornamento dei dispositivi](./media/device-update-4.png)

***Cmdlet***

[Approve-CsDeviceUpdateRule](/powershell/module/skype/approve-csdeviceupdaterule)

***Esempio***

```powershell
 Approve-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9
```

---

> **Scenario 5:** ripristinare gli aggiornamenti dei dispositivi

   ![Ripristinare l'aggiornamento dei dispositivi](./media/device-update-5.png)

***Cmdlet***

[Restore-CsDeviceUpdateRule](/powershell/module/skype/restore-csdeviceupdaterule)

***Esempio***

```powershell
 Restore-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9
```

---

## <a name="test-device"></a>Dispositivo di test

La voce di sottomenu **TEST DEVICE** consente agli amministratori di testare gli aggiornamenti del firmware prima che tali aggiornamenti siano distribuiti a tutti i dispositivi di un'organizzazione.

Prendiamo in considerazione le varie attività che un utente può eseguire su **TEST DEVICE** e i cmdlet Skype for Business a cui tali attività sono mappate.

---
> **Scenario 1:** elencare tutti i dispositivi di test

   ![List Test Device](./media/testdevice-1.png)

***Cmdlet***

[Get-CsTestDevice](/powershell/module/skype/get-cstestdevice)

***Esempio***

```powershell
 Get-CsTestDevice
```

---

> **Scenario 2:** creare un nuovo dispositivo di test

   ![Creare un dispositivo di test](./media/testdevice-2.png)

***Cmdlet***

[New-CsTestDevice](/powershell/module/skype/new-cstestdevice)  

***Esempio***

```powershell
 New-CsTestDevice -Identity site:Redmond/UCPhone -IdentifierType SerialNumber -Identifier "07823-A345"
```

---

> **Scenario 3:** ottenere i dettagli di un dispositivo di test scelto

   ![Ottenere il dispositivo di test](./media/testdevice-3.png)

***Cmdlet***

[Get-CsTestDevice](/powershell/module/skype/get-cstestdevice)

***Esempio***

```powershell
 Get-CsTestDevice -Identity site:Redmond/UCPhone
```

---

> **Scenario 4**: Eliminare i dispositivi di test scelti

   ![Elimina dispositivo di test](./media/testdevice-4.png)

***Cmdlet***

[Remove-CsTestDevice](/powershell/module/skype/remove-cstestdevice)

***Esempio***

```powershell
 Remove-CsTestDevice -Identity site:Redmond
```

---

> **Scenario 5:** aggiornare un dispositivo di test

   ![Aggiorna dispositivo di test](./media/testdevice-5.png)

***Cmdlet***

[Set-CsTestDevice](/powershell/module/skype/set-cstestdevice)

***Esempio***

```powershell
Set-CsTestDevice -Identity site:Redmond/UCPhone -IdentifierType SerialNumber -Identifier "09768-ABDR-83295"
```

---

## <a name="device-log-configuration"></a>Configurazione dei log del dispositivo

**La voce** del sottomenu DEVICE LOG CONFIGURATION consente di gestire il servizio Web Aggiornamento dispositivi, un componente di Skype for Business Server che consente agli amministratori di distribuire gli aggiornamenti del firmware ai telefoni e ad altri dispositivi che eseguono Skype for Business.

Prendiamo in considerazione le varie attività che un utente può eseguire su **DEVICE LOG CONFIGURATION** e i cmdlet Skype for Business a cui tali attività sono mappate.

---
> **Scenario 1:** elencare tutte le configurazioni dei log del dispositivo

   ![List Device Log Configuration](./media/device-log-configuration-1.png)

***Cmdlet***

[Get-CsDeviceUpdateConfiguration](/powershell/module/skype/get-csdeviceupdateconfiguration)

***Esempio***

```powershell
 Get-CsDeviceUpdateConfiguration
```

---

> **Scenario 2:** creare una nuova configurazione del log del dispositivo

   ![Creare la configurazione del registro dei dispositivi](./media/device-log-configuration-2.png)

***Cmdlet***

[New-CsDeviceUpdateConfiguration](/powershell/module/skype/new-csdeviceupdateconfiguration)  

***Esempio***

```powershell
 New-CsDeviceUpdateConfiguration -Identity site:Redmond "07823-A345"
```

---

> **Scenario 3:** ottenere i dettagli di una configurazione del log del dispositivo scelta

   ![Ottenere la configurazione del log del dispositivo](./media/device-log-configuration-3.png)

***Cmdlet***

[Get-CsDeviceUpdateConfiguration](/powershell/module/skype/get-csdeviceupdateconfiguration)

***Esempio***

```powershell
 Get-CsDeviceUpdateConfiguration -Identity Global
```

---

> **Scenario 4**: Eliminare le configurazioni dei log dei dispositivi scelte

   ![Delete Device Log Configuration](./media/device-log-configuration-4.png)

***Cmdlet***

[Remove-CsDeviceUpdateConfiguration](/powershell/module/skype/remove-csdeviceupdateconfiguration)

***Esempio***

```powershell
 Remove-CsDeviceUpdateConfiguration -Identity site:Redmond
```

---

> **Scenario 5:** aggiornare una configurazione del registro del dispositivo

   ![Aggiornare la configurazione del registro dei dispositivi](./media/device-log-configuration-5.png)

***Cmdlet***

[Set-CsDeviceUpdateConfiguration](/powershell/module/skype/set-csdeviceupdateconfiguration)

***Esempio***

```powershell
Set-CsDeviceUpdateConfiguration -Identity global -MaxLogFileSize 2048000 -MaxLogCacheLimit 1024000
```

---

## <a name="device-configuration"></a>Configurazione dispositivo

**La voce del** sottomenu DEVICE CONFIGURATION consente di amministrare le informazioni relative alle opzioni di gestione per i telefoni UC. Queste opzioni includono la modalità di sicurezza necessaria e se il telefono deve essere bloccato automaticamente dopo un periodo di inattività specificato.

Prendiamo in considerazione le varie attività che un utente può eseguire su **DEVICE CONFIGURATION** e i cmdlet Skype for Business a cui tali attività sono mappate.

---

> **Scenario 1:** elencare tutti i criteri per dispositivi mobili

   ![List Device Configuration](./media/device-configuration-1.png)

***Cmdlet***

[Get-CsUCPhoneConfiguration](/powershell/module/skype/get-csucphoneconfiguration)

***Esempio***

```powershell
 Get-CsUCPhoneConfiguration
```

---

> **Scenario 2:** creare una nuova configurazione del dispositivo

   ![Creare la configurazione del dispositivo](./media/device-configuration-2.png)

***Cmdlet***

[New-CsUCPhoneConfiguration](/powershell/module/skype/new-csucphoneconfiguration)  

***Esempio***

```powershell
 New-CsUCPhoneConfiguration -Identity site:Redmond -CalendarPollInterval "00:10:00" -LoggingLevel "Medium"
```

---

> **Scenario 3:** ottenere i dettagli di una configurazione del dispositivo scelta

   ![Ottenere la configurazione del dispositivo](./media/device-configuration-3.png)

***Cmdlet***

[Get-CsUCPhoneConfiguration](/powershell/module/skype/get-csucphoneconfiguration)

***Esempio***

```powershell
 Get-CsUCPhoneConfiguration -Identity site:Redmond
```

---

> **Scenario 4:** eliminare le configurazioni del dispositivo scelte

   ![Elimina configurazione dispositivo](./media/device-configuration-4.png)

***Cmdlet***

[Remove-CsUCPhoneConfiguration](/powershell/module/skype/remove-csucphoneconfiguration)

***Esempio***

```powershell
 Remove-CsUCPhoneConfiguration -Identity site:Redmond
```

---

> **Scenario 5:** aggiorna la configurazione di un dispositivo

   ![Aggiornare la configurazione del dispositivo](./media/device-configuration-5.png)

***Cmdlet***

[Set-CsUCPhoneConfiguration](/powershell/module/skype/set-csucphoneconfiguration)

***Esempio***

```powershell
 Set-CsUCPhoneConfiguration -Identity site:Redmond -PhoneLockTimeout "00:30:00"
```

---

## <a name="mobility-policy"></a>Criteri per dispositivi mobili

**I criteri di** mobilità determinano se un utente può usare o meno Skype for Business Mobile. Questi criteri gestiscono inoltre la capacità di un utente di utilizzare la funzionalità Chiamata tramite ufficio, che consente agli utenti di effettuare e ricevere chiamate telefoniche sul cellulare utilizzando il numero dell'ufficio anziché quello del cellulare. I criteri per dispositivi mobili possono essere utilizzati anche per rendere le Wi-Fi un requisito quando si effettuano o ricevono chiamate.

Prendere in considerazione le varie attività che un utente può eseguire su **CRITERI** DI MOBILITÀ e i cmdlet Skype for Business a cui tali attività sono mappate.

---

> **Scenario 1:** elencare tutti i criteri per dispositivi mobili

   ![Elencare i criteri per dispositivi mobili](media/mobility-policy-1.png)

***Cmdlet***

[Get-CsMobilityPolicy](/powershell/module/skype/get-csmobilitypolicy)

***Esempio***

```powershell
 Get-CsMobilityPolicy
```

---

> **Scenario 2:** creare un nuovo criterio per dispositivi mobili

   ![Creare criteri per dispositivi mobili](./media/mobility-policy-2.png)

***Cmdlet***

[New-CsMobilityPolicy](/powershell/module/skype/new-csmobilitypolicy)  

***Esempio***

```powershell
 New-CsMobilityPolicy -Identity site:Redmond -EnableOutsideVoice $False
```

---

> **Scenario 3:** ottenere i dettagli di un criterio per dispositivi mobili scelto

   ![Ottenere i criteri per dispositivi mobili](./media/mobility-policy-3.png)

***Cmdlet***

[Get-CsMobilityPolicy](/powershell/module/skype/get-csmobilitypolicy)

***Esempio***

```powershell
 Get-CsMobilityPolicy -Identity "site:Redmond"
```

---

> **Scenario 4**: Eliminare i criteri per dispositivi mobili scelti

   ![Eliminare i criteri per dispositivi mobili](./media/mobility-policy-4.png)

***Cmdlet***

[Remove-CsMobilityPolicy](/powershell/module/skype/remove-csmobilitypolicy)

***Esempio***

```powershell
 Remove-CsMobilityPolicy -Identity "site:Redmond"
```

---

> **Scenario 5:** aggiornare un criterio per dispositivi mobili

   ![Aggiornare i criteri per dispositivi mobili](./media/mobility-policy-5.png)

***Cmdlet***

[Set-CsMobilityPolicy](/powershell/module/skype/set-csmobilitypolicy)

***Esempio***

```powershell
Set-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False
```

---

## <a name="push-notification-configuration"></a>Configurazione notifica Push

Il servizio di notifica push (Servizio notifica Push Apple e Servizio notifica Push Microsoft) consente di inviare notifiche su eventi quali nuovi messaggi istantanei o nuovi messaggi vocali a dispositivi mobili come iPhone e telefoni Windows. Queste notifiche sono configurate per l'invio anche se l'applicazione Skype for Business su tali dispositivi è attualmente sospesa o in esecuzione in background.

Prendiamo in considerazione le varie attività che un utente può eseguire in CONFIGURAZIONE NOTIFICA **PUSH** e i cmdlet Skype for Business a cui tali attività sono mappate.

---

> **Scenario 1:** elencare tutti i criteri per dispositivi mobili

   ![Configurazione notifica Push elenco](./media/push-notification-config-1.png)

***Cmdlet***

[Get-CsPushNotificationConfiguration](/powershell/module/skype/get-cspushnotificationconfiguration)

***Esempio***

```powershell
 Get-CsPushNotificationConfiguration
```

---

> **Scenario 2:** creare una nuova configurazione di notifica push

   ![Creare la configurazione delle notifiche Push](./media/push-notification-config-2.png)

***Cmdlet***

[New-CsPushNotificationConfiguration](/powershell/module/skype/new-cspushnotificationconfiguration)  

***Esempio***

```powershell
 New-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService -$True
```

---

> **Scenario 3:** ottenere i dettagli di una configurazione di notifica push scelta

   ![Ottenere la configurazione delle notifiche Push](./media/push-notification-config-3.png)

***Cmdlet***

[Get-CsPushNotificationConfiguration](/powershell/module/skype/get-cspushnotificationconfiguration)

***Esempio***

```powershell
 Get-CsPushNotificationConfiguration -Identity "site:Redmond"
```

---

> **Scenario 4:** eliminare le configurazioni di notifica push scelte

   ![Delete Push Notification Configuration](./media/push-notification-config-4.png)

***Cmdlet***

[Remove-CsPushNotificationConfiguration](/powershell/module/skype/remove-cspushnotificationconfiguration)

***Esempio***

```powershell
 Remove-CsPushNotificationConfiguration -Identity "site:Redmond"
```

---

> **Scenario 5:** aggiornare una configurazione di notifica push

   ![Aggiornare la configurazione delle notifiche Push](./media/push-notification-config-5.png)

***Cmdlet***

[Set-CsPushNotificationConfiguration](/powershell/module/skype/set-cspushnotificationconfiguration)

***Esempio***

```powershell
 Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $False
```

---
