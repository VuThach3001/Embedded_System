# Cornell Notes

## Topic: CAN HW Objects Reduction

## Date: 15/09/2025

---

### Cue Column (Questions, Keywords, or Prompts)

---

### Notes Section (Main Notes)

**1. Motivation**

**Error:**
- A project faced a bct-error during integration of a new BC ComVeh:
```bash
Action-Id='Can_Validate': Error during oAW script execution Can_Validate.oaw: Execution of Can_Validate.oaw reported an error:
It is not allowed to configure more than 32 TxCanHardwareObjects in Dedicated Type of Tx buffer configuration for a node in the configured controller.
```
**Reason:**

- **Tx-Pdus**, part of the “PDU Ignore” in **comscl_netmtrx_rbands.xlsx**, **are not configured for TX-Multiplexing by rba_nds_gen** and therefore consume a dedicate hardware-object in the Can-Controller, leading to a hardware-object overflow.
- This violates the requirement: **Each Tx-Pdu shall be multiplexed**.

---

### Summary Section (Summary of Notes)

[Insert a brief summary of the key ideas and takeaways]
