# Production Crowdfunding - Implementation Plan

## 1. Core Templates

- [ ] **Token** — simple fungible token (owner, amount)
- [ ] **Campaign** — goal, deadline, creator
- [ ] **PledgeReceipt** — per backer (backer, amount, campaignCid)

## 2. Choices

- [ ] **Campaign:Create** — initialize campaign
- [ ] **Campaign:Pledge** — lock Token into campaign, create PledgeReceipt
- [ ] **Campaign:Collect** — creator claims all tokens if goal met
- [ ] **Campaign:CancelPledge** — backer releases their token before deadline
- [ ] **Campaign:Refund** — backer reclaims token after deadline if goal missed

## 3. Guards

- [ ] No duplicate pledge per backer
- [ ] Campaign deadline not in the past at creation
- [ ] Collect only after deadline & goal met
- [ ] Refund only after deadline & goal missed
- [ ] Cancel only before deadline
- [ ] PledgeReceipt can't be double-redeemed

## 4. Privacy

- [ ] Backers should not see each other's PledgeReceipt
- [ ] Use `observer` carefully — only creator sees aggregated info

## 5. Testing

- [ ] Test script: create campaign, pledge, collect (success path)
- [ ] Test script: create campaign, pledge, refund (failure path)
- [ ] Test script: cancel pledge before deadline
- [ ] Test script: duplicate pledge rejection
- [ ] Test script: privacy — verify backers can't see each other's receipts

## 6. Deployment

- [ ] Build `.dar` file
- [ ] Start local sandbox
- [ ] JSON API interaction

## 7. Bonus

- [ ] Reward tiers based on pledge amount
- [ ] Deadline extension by creator
- [ ] `abort` with descriptive error messages instead of bare `assert`
