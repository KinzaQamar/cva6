..
   Copyright 2024 Thales DIS France SAS
   Licensed under the Solderpad Hardware License, Version 2.1 (the "License");
   you may not use this file except in compliance with the License.
   SPDX-License-Identifier: Apache-2.0 WITH SHL-2.1
   You may obtain a copy of the License at https://solderpad.org/licenses/

   Original Author: Jean-Roch COULON - Thales

.. _CVA6_bht_ports:

.. list-table:: bht module IO ports
   :header-rows: 1

   * - Signal
     - IO
     - Description
     - connexion
     - Type

   * - ``clk_i``
     - in
     - Subsystem Clock
     - SUBSYSTEM
     - logic

   * - ``rst_ni``
     - in
     - Asynchronous reset active low
     - SUBSYSTEM
     - logic

   * - ``flush_i``
     - in
     - Fetch flush request
     - CONTROLLER
     - logic

   * - ``vpc_i``
     - in
     - Virtual PC
     - CACHE
     - logic[riscv::VLEN-1:0]

   * - ``bht_update_i``
     - in
     - Update bht with resolved address
     - EXECUTE
     - ariane_pkg::bht_update_t

   * - ``bht_prediction_o``
     - out
     - Prediction from bht
     - FRONTEND
     - ariane_pkg::bht_prediction_t[ariane_pkg::INSTR_PER_FETCH-1:0]

Due to cv32a65x configuration, some ports are tied to a static value. These ports do not appear in the above table, they are listed below

| As DebugEn = 0,
|   ``debug_mode_i`` input is tied to 0
