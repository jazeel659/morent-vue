<template>
    <div class="selector-wrapper">
        <div class="title">
            <div class="radio"></div>
            <h3>{{ label }}</h3>
        </div>
        <div class="details">
            <div class="locations-picker">
                Locations
                <NSelect placeholder="Select your city" />
            </div>
            <div class="date-picker">
                Date
                <NDatePicker />
            </div>
            <div class="time-picker">
                Time
                <NTimePicker />
            </div>

        </div>
    </div>
</template>
<script>
import { NButton, NDatePicker, NTimePicker, NSelect } from 'naive-ui'
export default {
    props: {
        label: String
    },
    components: {
        NButton,
        NDatePicker,
        NTimePicker,
        NSelect
    }
}
</script>
<style>
.selector-wrapper {
    background: #FFFFFF;
    border-radius: 10px;
    padding: 24px 48px;

}

.selector-wrapper .details {
    display: flex;
    align-items: center;
    column-gap: 20px;
}

.details .locations-picker {
    flex: 1;
    font-weight: bold;
}

.n-base-selection .n-base-selection-overlay {
    padding-left: 0;
}

.n-base-selection .n-base-selection__border,
.n-base-selection .n-base-selection__state-border {
    border: none;
}

.details .locations-picker .n-select {
    width: 120px;
    height: 20px;

}

.details .date-picker {
    flex: 1;
    font-weight: bold;
}

.details .time-picker {
    flex: 1;
    font-weight: bold;
}

.title {
    display: flex;
    align-items: center;
    column-gap: 5px;
    margin-bottom: 16px;
}

.title .radio {
    height: 16px;
    width: 16px;
    background-color: #3563E9;
    border-radius: 8px;
    border: 4px solid #c2d0f8;
}


.title h3 {
    font-family: 'Plus Jakarta Sans';
    font-style: normal;
    font-weight: 600;
    font-size: 16px;
    line-height: 150%;
}
</style>