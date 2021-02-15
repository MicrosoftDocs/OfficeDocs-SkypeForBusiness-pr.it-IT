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
description: Informazioni sulla funzione Skype Meeting Broadcast di Skype for Business online che consente di pianificare, produrre e trasmettere riunioni o eventi a un vasto pubblico online, fino a un massimo di 10.000 partecipanti.
ms.openlocfilehash: b774c368674f421c11f36339ef7188ea8de82e64
ms.sourcegitcommit: ab566ddab9d26440bac1716a975f30e075d0c7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865160"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a>Configurare la rete per Skype Meeting Broadcast

Dopo aver [abilitato Skype Meeting Broadcast](enable-skype-meeting-broadcast.md) Skype Meeting Broadcast, devi configurare la rete. Fai questo passaggio se vuoi tenere webinar e altre trasmissioni per persone esterne alla tua azienda.

> [!IMPORTANT]
> Skype for Business online verrà ritirato il 31 luglio 2021, data in cui l'accesso al servizio terminerà. Consigliamo ai clienti di iniziare l'aggiornamento a Microsoft Teams, il client principale per le comunicazioni e il lavoro in team in Microsoft 365.

Se non hai esperienza nella configurazione del firewall, può essere utile assumere un [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) per fare questo passaggio.

Per ignorare questo passaggio e aggiungere un'altra azienda alla federazione in modo da poter invitare gli utenti alle trasmissioni, seguire la procedura descritta in Consentire agli utenti di contattare utenti [Skype for Business esterni.](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

## <a name="step-1-set-up-allowed-domains"></a>Passaggio 1: Configurare i domini consentiti

Usare **uno** dei metodi seguenti per configurare i domini consentiti:

## #

 **Metodo 1: Usare l'interfaccia di amministrazione**

1. Accedi all'interfaccia di amministrazione, quindi nel riquadro di spostamento sinistro fai clic su **Componenti** aggiuntivi Servizi di impostazioni e quindi scegli Skype for  >  **&amp;** **Business.**

2. Nella pagina **Condivisione esterna** in Eccezioni dominio **selezionare** Tutti i domini sono bloccati ad eccezione di **e** immettere i domini seguenti, separati da una virgola (,):

   - noammeetings.lync.com

   - emeameetings.lync.com

   - apacmeetings.lync.com

   - resources.lync.com

3. Fare clic su **Salva**.

## #

 **Metodo 2: usare Windows PowerShell**

- Nel **menu Start fare clic con** il pulsante destro del mouse **Windows PowerShell** e scegliere Esegui **come amministratore.** Nella finestra **Windows PowerShell** testo digitare ogni riga e premere INVIO.

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

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a>Passaggio 2: Aggiungere domini, URL e indirizzi IP di Skype Meeting Broadcast

Il secondo passaggio del processo di configurazione consiste nell'aggiungere prima i domini necessari e quindi aggiungere gli indirizzi IP e gli URL necessari per il funzionamento di Skype Meeting Broadcast.

- **Aggiungere gli URL e gli indirizzi IP necessari per** gli endpoint di Skype for Business online, facendo clic qui per vedere quali sono [necessari.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a>Configurare Skype Meeting Broadcast in organizzazioni e distribuzioni ibride

Se si dispone di un'organizzazione Skype for Business online e di una distribuzione locale di Lync Server 2010, Microsoft Lync Server 2013 e Skype for Business Server 2015 con utenti sia online che locali, oltre a quelli precedenti è necessario eseguire altre operazioni di configurazione per consentire all'organizzazione locale di comunicare con Skype for Business online e consentire a tutti gli utenti di partecipare a un evento Skype Meeting Broadcast. Per sapere quali sono questi requisiti, vedi Configurare la distribuzione [locale di Skype Meeting Broadcast.](https://go.microsoft.com/fwlink/?LinkId=617070)

## <a name="related-topics"></a>Argomenti correlati

[Abilitare Skype Meeting Broadcast](enable-skype-meeting-broadcast.md)

[URL e intervalli di indirizzi IP per Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[Configurare Skype for Business online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)



