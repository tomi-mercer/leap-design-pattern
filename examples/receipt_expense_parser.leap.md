<LEAP_FILE type="leaplet_example_parser">
<DOMINO>
    <TEMPLATE>
        <RECIPE_CARD>
            <MAP>
                <FUEL>
                    <!-- [PASTE_RAW_OCR_RECEIPT_TEXT_HERE] -->
                </FUEL>

                <THE_MACHINE>
                    <LOGIC>
                        1. **Merchant Identification**: Locate the primary business name at the top of the receipt.
                        2. **Currency Extraction**: Isolate the Total Amount and the Tax Amount.
                        3. **Temporal Mapping**: Find the transaction date and time.
                        4. **Category Assignment**: Predict the expense category (e.g., Travel, Meals, Office Supplies).
                    </LOGIC>
                </THE_MACHINE>

                <THE_DESTINATION>
                    <OUTPUT_FORMAT>
                        | Field | Value |
                        | :--- | :--- |
                        | Merchant | |
                        | Date | |
                        | Total | |
                        | Tax | |
                        | Category | |
                    </OUTPUT_FORMAT>
                </THE_DESTINATION>
            </MAP>
        </RECIPE_CARD>
    </TEMPLATE>
</DOMINO>
</LEAP_FILE>
