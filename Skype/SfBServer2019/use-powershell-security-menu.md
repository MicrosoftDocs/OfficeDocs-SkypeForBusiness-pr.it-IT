---
title: Usare PowerShell per le attività nel menu Sicurezza
ms.reviewer: ''
ms.author: ankum
author: ankum
manager: ravrao
ms.date: 11/03/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: ''
description: 'Riepilogo: Skype for Business Server pannello di controllo al mapping cmdlet per il menu Sicurezza.'
ms.openlocfilehash: 6e726b13b9428b213011126abf5ac0869e6cfbf8
ms.sourcegitcommit: eba9fc680233e9e03773a2942f22afe6247eec41
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60824933"
---
# <a name="security"></a>Sicurezza

In questo articolo viene descritto come ottenere risultati simili a quelli della voce **di** menu Sicurezza nel Pannello di controllo legacy utilizzando i cmdlet.

In questo articolo vengono descritti i sottomenu seguenti:

- [Sicurezza](#security)
  - [Registrar](#registrar)
  - [Web Service](#web-service)
  - [Criteri PIN](#pin-policy)

## <a name="registrar"></a>Registrar

**Il** sottomenu REGISTRAR consente agli amministratori di gestire i server proxy tramite le impostazioni di configurazione del server proxy. Queste impostazioni, che possono essere applicate sia nell'ambito globale che nell'ambito del servizio (anche se solo per il server perimetrale e i servizi di registrazione) consentono di controllare aspetti quali i protocolli di autenticazione che possono essere utilizzati dagli endpoint client e se verrà utilizzata o meno la compressione nelle connessioni al server proxy in ingresso e in uscita.

Prendere in considerazione le varie attività che un utente può eseguire su **REGISTRAR** e i cmdlet Skype for Business a cui tali attività sono mappate.

---

> **Scenario 1:** elencare tutte le configurazioni proxy

   ![Configurazione proxy elenco](./media/proxy-configurations-1.png)

***Cmdlet***

[Get-CsProxyConfiguration](/powershell/module/skype/get-csproxyconfiguration)

***Esempio***

```powershell
 Get-CsProxyConfiguration
```

---

> **Scenario 2**: Creare una nuova configurazione proxy

   ![Creare la configurazione proxy](./media/proxy-configurations-2.png)

***Cmdlet***

[New-CsProxyConfiguration](/powershell/module/skype/new-csproxyconfiguration)  

***Esempio***

```powershell
 New-CsProxyConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -RequestServerCompression $True -MaxClientMessageBodySizeKb 256
```

---

> **Scenario 3:** ottenere i dettagli di una configurazione proxy scelta

   ![Ottieni configurazione proxy](./media/proxy-configurations-3.png)

***Cmdlet***

[Get-CsProxyConfiguration](/powershell/module/skype/get-csproxyconfiguration)

***Esempio***

```powershell
 Get-CsProxyConfiguration -Identity "service:EdgeServer:atl-cs-001.litwareinc.com"
```

---

> **Scenario 4**: Eliminare le configurazioni proxy scelte

   ![Elimina configurazione proxy](./media/proxy-configurations-4.png)

***Cmdlet***

[Remove-CsProxyConfiguration](/powershell/module/skype/remove-csproxyconfiguration)

***Esempio***

```powershell
 Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
```

---

> **Scenario 5:** aggiornare una configurazione proxy

   ![Aggiornare la configurazione del proxy](./media/proxy-configurations-5.png)

***Cmdlet***

[Set-CsProxyConfiguration](/powershell/module/skype/set-csproxyconfiguration)

***Esempio***

```powershell
 Set-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-001.litwareinc.com -AcceptServerCompression $True
```

---

## <a name="web-service"></a>Web Service

La **voce del** sottomenu SERVIZIO WEB in Sicurezza consente agli amministratori di gestire le impostazioni di configurazione dei servizi Web in tutta l'organizzazione.  ciò include la gestione dell'espansione del gruppo, delle impostazioni dei certificati e dei metodi di autenticazione consentiti. Poiché gli amministratori possono configurare impostazioni diverse nell'ambito globale, del sito e del servizio (anche se solo per il servizio Servizi Web), è possibile personalizzare le funzionalità dei servizi Web per utenti diversi e posizioni diverse.

Prendere in considerazione le varie attività che un utente può eseguire su **WEB SERVICE** e i cmdlet Skype for Business a cui tali attività sono mappate.

---
> **Scenario 1:** elencare tutte le configurazioni del servizio Web

   ![Configurazione del servizio Web elenco](./media/web-service-1.png)

***Cmdlet***

[Get-CsWebServiceConfiguration](/powershell/module/skype/get-cswebserviceconfiguration)

***Esempio***

```powershell
 Get-CsWebServiceConfiguration
```

---

> **Scenario 2:** creare una nuova configurazione del servizio Web

   ![Nuova configurazione del servizio Web](./media/web-service-2.png)

***Cmdlet***

[New-CsWebServiceConfiguration](/powershell/module/skype/new-cswebserviceconfiguration)  

***Esempio***

```powershell
 New-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $False -UseCertificateAuth $True
```

---

> **Scenario 3:** ottenere i dettagli di una configurazione del servizio Web scelta

   ![Ottenere la configurazione del servizio Web](./media/web-service-3.png)

***Cmdlet***

[Get-CsWebServiceConfiguration](/powershell/module/skype/get-cswebserviceconfiguration)

***Esempio***

```powershell
 Get-CsWebServiceConfiguration -Identity site:Redmond
```

---

> **Scenario 4**: Eliminare le configurazioni del servizio Web scelte

   ![Eliminare la configurazione del servizio Web](./media/web-service-4.png)

***Cmdlet***

[Remove-CsWebServiceConfiguration](/powershell/module/skype/remove-cswebserviceconfiguration)

***Esempio***

```powershell
 Remove-CsWebServiceConfiguration -Identity site:Redmond
```

---

> **Scenario 5:** aggiornare la configurazione di un servizio Web

   ![Aggiornare la configurazione del servizio Web](./media/Web-service-5.png)

***Cmdlet***

[Set-CsWebServiceConfiguration](/powershell/module/skype/set-cswebserviceconfiguration)

***Esempio***

```powershell
 Set-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $True
```

---

## <a name="pin-policy"></a>Criteri PIN

Gli amministratori possono usare **CRITERI PIN** per gestire le proprietà di autenticazione del PIN; ad esempio, è possibile specificare la lunghezza minima per un PIN e determinare se uno consentirà i PIN che utilizzano "modelli comuni" come le cifre consecutive (ad esempio, un PIN come 123456)

Prendiamo in considerazione le varie attività che un utente può eseguire su **CRITERI PIN** e i cmdlet Skype for Business a cui tali attività sono mappate.

---

> **Scenario 1:** elencare tutti i criteri PIN

   ![Criteri pin elenco](./media/pin-policy-1.png)

***Cmdlet***

[Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy)

***Esempio***

```powershell
 Get-CsPinPolicy
```

---

> **Scenario 2:** creare un nuovo criterio PIN

   ![Creare criteri pin](./media/pin-policy-2.png)

***Cmdlet***

[New-CsPinPolicy](/powershell/module/skype/new-cspinpolicy)  

***Esempio***

```powershell
 New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 10
```

---

> **Scenario 3:** ottenere i dettagli di un criterio PIN scelto

   ![Ottenere criteri PIN](./media/pin-policy-3.png)

***Cmdlet***

[Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy)

***Esempio***

```powershell
 Get-CsPinPolicy -Identity "site:Redmond"
```

---

> **Scenario 4**: Eliminare i criteri PIN scelti

   ![Elimina criteri PIN](./media/pin-policy-4.png)

***Cmdlet***

[Remove-CsPinPolicy](/powershell/module/skype/remove-cspinpolicy)

***Esempio***

```powershell
 Remove-CsPinPolicy -Identity RedmondUsersPinPolicy
```

---

> **Scenario 5:** aggiornare un criterio PIN

   ![Aggiornare i criteri PIN](./media/pin-policy-5.png)

***Cmdlet***

[Set-CsPinPolicy](/powershell/module/skype/set-cspinpolicy)

***Esempio***

```powershell
 Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

---
