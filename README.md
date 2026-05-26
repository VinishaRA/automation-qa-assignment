# Task 2 — n8n API Integration Workflow

## Overview

This workflow automates cryptocurrency monitoring using CoinGecko public APIs and sends alerts to Discord.

## Workflow Logic

1. A Schedule Trigger runs every 1 hour.
2. The first HTTP Request fetches cryptocurrency market data from the CoinGecko Markets API.
3. A JavaScript Code node filters and transforms the response to keep the top 5 coins.
4. A second HTTP Request enriches the selected coin using another CoinGecko endpoint.
5. An IF node checks whether the market capitalization exceeds a threshold.
6. Different Discord alerts are sent based on the condition.
7. Error handling is implemented using “On Error → Continue” in HTTP Request nodes.

## APIs Used

* CoinGecko Markets API
* CoinGecko Coin Details API

## Notification Channel

* Discord Webhook

## Error Handling

The workflow uses “On Error → Continue” in HTTP Request nodes to prevent silent workflow failures.
