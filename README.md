# CSC1401-Assign3

<html>


<head>
    <script>
        var list = [];

        function addAppointment() {
            var appointmentData = {};

            var inputDate = document.getElementById('date').value;
            appointmentData.date = inputDate;
            var inputStartTime = document.getElementById('startTime').selectedIndex;
            appointmentData.startTime = inputStartTime;
            var inputEndTime = document.getElementById('endTime').selectedIndex;
            appointmentData.endTime = inputEndTime;
            var inputSubject = document.getElementById('subject');
            appointmentData.subject = inputSubject;
            var inputVenue = document.getElementById('venue');
            appointmentData.venue = inputVenue;

            if (document.getElementById('high').check) {
                var priority = 'High'
            }
            else if (document.getElementById('medium').check) {
                var priority = 'Medium'
            }
            else if (document.getElementById('low').check) {
                var priority = 'Low'
            }

            list.push(appointmentData);
        }

        console.log("list",list)

        

        function addData(data) {
            const mainTBody = document.getElementById("mainTBody");
        

        for (var i = 0; i < data.length; i++) {
				var tr = document.createElement("tr");
				tr.innerHTML = `
				<td>${data[i].date}</td>
				<td>${data[i].startTime}</td>
				<td>${data[i].endTime}</td>
                <td>${data[i].subject}</td>
                <td>${data[i].venue}</td>
                `;
        
				mainTBody.append(tr);
            }
            
        }
        addData(list);

    </script>



</head>






<body>

    <title>Diary</title>
    <h1 style="text-align: center;">Diary</h1>
    <form>
        <table bgcolor="#cccccc" cellpadding="5" cellspacing="0" align="center">
            <tr>
                <td align="right">Date</td>
                <td><input type="date" id="date" size="10" min="2020-01-01"></td>
                <td align="right">Start Time</td>
                <td>
                    <select id="startTime">
                        <option value="00:00">00:00</option>
                        <option value="01:00">01:00</option>
                        <option value="02:00">02:00</option>
                        <option value="03:00">03:00</option>
                        <option value="04:00">04:00</option>
                        <option value="05:00">05:00</option>
                        <option value="06:00">06:00</option>
                        <option value="07:00">07:00</option>
                        <option value="08:00">08:00</option>
                        <option value="09:00">09:00</option>
                        <option value="10:00">10:00</option>
                        <option value="11:00">11:00</option>
                        <option value="12:00">12:00</option>
                        <option value="13:00">13:00</option>
                        <option value="14:00">14:00</option>
                        <option value="15:00">15:00</option>
                        <option value="16:00">16:00</option>
                        <option value="17:00">17:00</option>
                        <option value="18:00">18:00</option>
                        <option value="19:00">19:00</option>
                        <option value="20:00">20:00</option>
                        <option value="21:00">21:00</option>
                        <option value="22:00">22:00</option>
                        <option value="23:00">23:00</option>
                    </select>
                </td>
                <td align="right">End Time</td>
                <td>
                    <select id="endTime">
                        <option value="00:00">00:00</option>
                        <option value="01:00">01:00</option>
                        <option value="02:00">02:00</option>
                        <option value="03:00">03:00</option>
                        <option value="04:00">04:00</option>
                        <option value="05:00">05:00</option>
                        <option value="06:00">06:00</option>
                        <option value="07:00">07:00</option>
                        <option value="08:00">08:00</option>
                        <option value="09:00">09:00</option>
                        <option value="10:00">10:00</option>
                        <option value="11:00">11:00</option>
                        <option value="12:00">12:00</option>
                        <option value="13:00">13:00</option>
                        <option value="14:00">14:00</option>
                        <option value="15:00">15:00</option>
                        <option value="16:00">16:00</option>
                        <option value="17:00">17:00</option>
                        <option value="18:00">18:00</option>
                        <option value="19:00">19:00</option>
                        <option value="20:00">20:00</option>
                        <option value="21:00">21:00</option>
                        <option value="22:00">22:00</option>
                        <option value="23:00">23:00</option>
                    </select>
                </td>

            </tr>
            <tr>
                <td align="right">Subject:</td>
                <td><input type="text" id="subject" size="10"></td>
            </tr>
            <tr>
                <td align="right">Venue:</td>
                <td><input type="text" id="venue" size="10"></td>
            </tr>
            <tr>
                <td valign="top" align="center">Priority</td>
                <td><input type="radio" id="high" name="Priority" checked />High<br />
                <td><input type="radio" id="medium" name="Priority" checked />Medium<br />
                <td><input type="radio" id="low" name="Priority" checked />Low<br />
                </td>
            </tr>

        </table>
        <tr>
            <td></td>
            <td></td><input type="submit" value="Add Appointment" onclick="addAppointment()" /></td>
        </tr>


        <hr>

        <table align="center" width="80%" height="150px" cellpadding="1px" cellspacing="1px" border="1" id="table1">
            <thead>
                <tr>
                    <th width="50">Date</th>
                    <th width="20">Start</th>
                    <th width="20">End</th>
                    <th width="75">Subject</th>
                    <th width="60">Venue</th>
                    <th width="5">Priority</th>
                </tr>
            </thead>
            <tbody id="mainTBody"></tbody>
        </table>
        <tr>
            <td></td>
            <td></td><input type="reset" value="Randomise Appointments" onclick="shuffleAppointments()" /></td>
            <td></td><input type="button" value="Sort Appointments" onclick="sortRecords()" /></td>
            <td>by</td>
            <td>
                <select id="Date">
                    <option value="date">Date</option>
                    <option value="startTime">Start Time</option>
                    <option value="endTime">End Time</option>
                    <option value="subject">Subject</option>
                    <option value="venue">Venue</option>
                    <option value="priority">Priority</option>
                </select>
            </td>
        </tr>
        <hr>



        <table>
            <th width="50">Date</th>
            <th width="20">Year</th>
            <th width="20">Appointment</th>


            </hr>




        </table>
    </form>

</body>
