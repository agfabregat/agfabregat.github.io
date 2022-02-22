    var _ts1minute = 60 * 1000;
    var _ts1hour = 60 * _ts1minute;
    var _ts1day = 24 * _ts1hour;
    var _ts1month = 30 * _ts1day;
    var _ts1year = 365 * _ts1day;

    var tsMssgs = ['seconds ago', 'minute ago', 'minutes ago', 'hour ago', 'hours ago', 'day ago', 'days ago', 'month ago', 'months ago', 'year ago', 'years ago'];

class TS
{
    constructor(time, mssg)
    {
        this.time = time;
        this.mssg = mssg;
    }
}

function timeAgo(now, postDate)
{

    var elapsed = now - postDate;
    if (elapsed < _ts1minute)
    {
        return new TS('', 0);
    }
    else
    {
        if (elapsed < _ts1hour)
        {

            var minutes = Math.floor(elapsed / _ts1minute);
            var minutesMsg = 1;
            if (minutes > 1) { minutesMsg = 2; }
            return new TS(minutes, minutesMsg);
        }
        else
        {
            if (elapsed < _ts1day)
            {
                var hours = Math.floor(elapsed / _ts1hour);
                var hoursMsg = 3;
                if (hours > 1)
                {
                    hoursMsg = 4;
                }
                return new TS(hours, hoursMsg);

            }
            else
            {
                if (elapsed < _ts1month)
                {
                    var days = Math.floor(elapsed / _ts1day);
                    var daysMsg = 5;
                    if (days > 1)
                    {
                        daysMsg = 6;
                    }
                    return new TS(days, daysMsg);
                }
                else
                {
                    if (elapsed < _ts1year)
                    {
                        var months = Math.floor(elapsed / _ts1month);
                        var monthsMsg = 7;
                        if (months > 1)
                        {
                            monthsMsg = 8;
                        }
                        return new TS(months, monthsMsg);
                    }
                    else
                    {
                        var years = Math.floor(elapsed / _ts1year);
                        var yearsMsg = 9;
                        if (years > 1)
                        {
                            yearsMsg = 10;
                        }
                        return new TS(years, yearsMsg);
                    }
                }
            }
        }
    }
}

var now = Date.now();

var tss = document.getElementsByClassName("ts");


function RunTimeAgo()
{
    now = Date.now();
    for (var i = tss.length - 1; i > -1; i--)
    {
        if (tss[i].classList.contains('ts'))
        {
            var isoTs = tss[i].dataset.ts;
            isoPostDate = parseInt(isoTs, 10);
            tsObj = timeAgo(now, isoPostDate);
            tss[i].textContent = tsObj.time + ' ' + tsMssgs[tsObj.mssg];
            if (tsObj.mssg > 4)
            {
                tss[i].classList.remove('ts');
            }
        }
    }
}


        function cbToggle()
        {
            if (toggle.checked == true){
                menurow.style.display = "block";
            } else
            {
                menurow.style.display = "none";
            }
        }

    document.addEventListener("DOMContentLoaded", function(event) {
        // Your code to run since DOM is loaded and ready
        let menurow = document.getElementById("menurow");
        let toggle = document.getElementById("toggle");

        RunTimeAgo();
        var timerID = setInterval(function() {
            RunTimeAgo();
        }, _ts1minute);

    });
