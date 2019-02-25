<script>
export default {

  props: {
    parentEl: {
      type: String,
      default: 'body',
    },
    element: {
      type: String,
      // this.element = $(element);
      default: '',
    },
    startDate: {
      type: ['String', moment],
      default () {
        // TODO moment.utc() or moment()
        return moment().startOf('day');
      },
    },
    endDate: {
      type: [String, moment],
      default () {
        // TODO moment.utc() or moment()
        // TODO endOf ??
        return moment().endOf('day');
      },
    },
    minDate: {
      type: [String, Object],
      default () {
        return '';
      },
    },
    maxDate: {
      type: [String, Object],
      default () {
        return '';
      },
    },
    maxSpan: {
      type: Object,
      default () {
        return {};
      },
    },
    minYear: {
      type: [Number, String],
      default: moment().subtract(100, 'year').format('YYYY'),
    },
    maxYear: {
      type: [Number, String],
      default: moment().add(100, 'year').format('YYYY'),
    },
    autoApply: {
      type: Boolean,
      default: false,
    },
    singleDatePicker: {
      type: Boolean,
      default: false,
    },
    showDropdowns: {
      type: Boolean,
      default: false,
    },
    showWeekNumbers: {
      type: Boolean,
      default: false,
    },
    showISOWeekNumbers: {
      type: Boolean,
      default: false,
    },
    showCustomRangeLabel: {
      type: Boolean,
      default: false,
    },
    timePicker: {
      type: Boolean,
      default: false,
    },
    timePicker24Hour: {
      type: Boolean,
      default: false,
    },
    timePickerSeconds: {
      type: Boolean,
      default: false,
    },
    timePickerIncrement: {
      type: [Number],
      default: 1,
    },
    linkedCalendars: {
      type: Boolean,
      default: false,
    },
    autoUpdateInput: {
      type: Boolean,
      default: false,
    },
    alwaysShowCalendars: {
      type: Boolean,
      default: false,
    },
    ranges: {
      type: Object,
      // TODO 这种 object 是真的希望被 watch 吗
      default () {
        return {};
      },
    },
    isCustomDate: {
      type: Function,
      default: function() {},
    },
    isInvalidDate: {
      type: Function,
      default: function() { return false; },
    },
    callback: {
      type: Function,
      default: function() { return false; },
    },
    opens: {
      type: String,
      default: 'right',
    },
    drops: {
      type: String,
      default: 'down',
    },
    buttonClasses: {
      type: String,
      default: 'btn-primary',
    },
    cancelButtonClasses: {
      type: String,
      default: 'btn-default',
    },
    locale: {
      type: Object,
      default () {
        return {
          direction: 'ltr',
          format: moment.localeData().longDateFormat('L'),
          separator: ' - ',
          applyLabel: 'Apply',
          cancelLabel: 'Cancel',
          weekLabel: 'W',
          customRangeLabel: 'Custom Range',
          daysOfWeek: moment.weekdaysMin(),
          monthNames: moment.monthsShort(),
          firstDay: moment.localeData().firstDayOfWeek()
        };
      },
    },
    options: {
      type: Object,
      default () {
        return {};
      },
    },
  }
}
</script>
