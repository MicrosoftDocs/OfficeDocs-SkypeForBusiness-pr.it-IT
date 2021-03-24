---
title: Configurare la rete per Skype Meeting Broadcast
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: dfa736b9-4920-4f48-b8c0-b5487ec6086f
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- SMB
description: Informazioni sulla funzionalità Skype Meeting Broadcast di Skype for Business online che consente di pianificare, produrre e trasmettere riunioni o eventi a un pubblico online di grandi dimensioni fino a 10.000 partecipanti.
ms.openlocfilehash: 513b6f8d677550557293855389eff29dc61c21c1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106512"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a>Configurare la rete per Skype Meeting Broadcast

Dopo aver [abilitato Skype Meeting Broadcast](enable-skype-meeting-broadcast.md) Skype Meeting Broadcast, è necessario configurare la rete. Eseguire questo passaggio se si vogliono tenere webinar e altre trasmissioni per utenti esterni all'azienda.

> [!IMPORTANT]
> Skype for Business online è in ritiro il 31 luglio 2021, quando l'accesso al servizio terminerà. Incoraggiamo i clienti a iniziare l'aggiornamento a Microsoft Teams, il client principale per le comunicazioni e il lavoro in team in Microsoft 365.

Se non si ha esperienza nella configurazione del firewall, è consigliabile assumere un [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) per eseguire questo passaggio.

Per ignorare questo passaggio e aggiungere un'altra attività alla federazione in modo da poterle invitare a trasmettere, seguire la procedura descritta in Consentire agli utenti di contattare utenti [esterni di Skype for Business.](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

## <a name="step-1-set-up-allowed-domains"></a>Passaggio 1: Configurare i domini consentiti

Usare **uno** dei metodi seguenti per configurare i domini consentiti:

## #

 **Metodo 1: Usare l'interfaccia di amministrazione**

1. Passare all'interfaccia di amministrazione e quindi nel riquadro di spostamento sinistro fare clic su Componenti aggiuntivi Servizi impostazioni e quindi scegliere Skype for  >  **&amp;** **Business.**

2. Nella pagina **Condivisione esterna** in **Eccezioni** dominio selezionare Tutti i domini sono bloccati tranne **e** immettere i domini seguenti, separati da una virgola (,):

   - noammeetings.lync.com

   - emeameetings.lync.com

   - apacmeetings.lync.com

   - resources.lync.com

3. Fare clic su **Salva**.

## #

 **Metodo 2: Usare Windows PowerShell**

- Nel **menu Start fare clic con** il pulsante destro **Windows PowerShell** clic su Esegui **come amministratore.** Nella finestra **Windows PowerShell** digitare ogni riga e premere INVIO.

  ```PowerShell
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```PowerShell
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```PowerShell
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```PowerShell
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```PowerShell
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```PowerShell
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a>Passaggio 2: Aggiungere domini, URL e indirizzi IP Skype Meeting Broadcast

Il secondo passaggio del processo di configurazione consiste nell'aggiungere prima i domini necessari e quindi aggiungere gli indirizzi IP e gli URL necessari per il funzionamento di Skype Meeting Broadcast.

- **Aggiungere gli URL degli endpoint e** gli indirizzi IP di Skype for Business Online necessari per vedere quali sono necessari [qui.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a>Configurare Skype Meeting Broadcast nelle distribuzioni ibride e nelle organizzazioni

Se si ha un'organizzazione Skype for Business Online e una distribuzione locale di Lync Server 2010, Microsoft Lync Server 2013 e Skype for Business Server 2015 e si hanno utenti sia online che locali, è necessario eseguire altre operazioni di configurazione oltre a quelle precedenti per consentire all'organizzazione locale di comunicare con Skype for Business Online e consentire a tutti gli utenti di partecipare a Skype Meeting Broadcast. Per sapere quali sono questi requisiti, consulta Configurare la distribuzione [locale per Skype Meeting Broadcast.](../../SfbServer/deploy/configure-skype-meeting-broadcast.md)

## <a name="related-topics"></a>Argomenti correlati

[Abilitare Skype Meeting Broadcast](enable-skype-meeting-broadcast.md)

[URL e intervalli di indirizzi IP per Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[Configurare Skype for Business online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)